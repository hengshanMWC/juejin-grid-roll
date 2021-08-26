<template>
  <div id="app">
    <div class="left_part">
      <div class="lottery">
        <div class="turntable-box">
          <div class="upper-border up-down">
            <div class="dot vertex"></div>
            <div class="dot border left-border-dot"></div>
            <div class="dot white"></div>
            <div class="dot border right-border-dot"></div>
            <div class="dot vertex"></div>
          </div>
          <div data-v-2770fad3="" class="lower-border up-down">
            <div data-v-2770fad3="" class="dot vertex"></div>
            <div data-v-2770fad3="" class="dot border left-border-dot"></div>
            <div data-v-2770fad3="" class="dot white"></div>
            <div data-v-2770fad3="" class="dot border right-border-dot"></div>
            <div data-v-2770fad3="" class="dot vertex"></div>
          </div>
          <div data-v-2770fad3="" class="left-border left-right">
            <div data-v-2770fad3="" class="dot vertex"></div>
            <div data-v-2770fad3="" class="dot border left-border-dot"></div>
            <div data-v-2770fad3="" class="dot white"></div>
            <div data-v-2770fad3="" class="dot border right-border-dot"></div>
            <div data-v-2770fad3="" class="dot vertex"></div>
          </div>
          <div data-v-2770fad3="" class="right-border left-right">
            <div data-v-2770fad3="" class="dot vertex"></div>
            <div data-v-2770fad3="" class="dot border left-border-dot"></div>
            <div data-v-2770fad3="" class="dot white"></div>
            <div data-v-2770fad3="" class="dot border right-border-dot"></div>
            <div data-v-2770fad3="" class="dot vertex"></div>
          </div>
          <div class="blocks">
            <div class="item-container">
              <gridRoll interval="6px" ref="dial">
                <template v-slot:button>
                  <gridStart>
                    <div
                      @click="handleLottery"
                      class="turntable-item item lottery"
                    >
                      <div class="lottery-text">抽奖</div>
                      <div class="text">200矿石1次</div>
                    </div>
                  </gridStart>
                </template>
                <template v-slot:prize>
                  <gridPrize
                    v-for="prize in prizes"
                    :key="prize.id"
                    :pid="prize.id"
                    :disabled="prize.disabled"
                  >
                    <template v-slot="{ isSelect }">
                      <div
                        class="turntable-item item"
                        :class="{ chosen: isSelect }"
                      >
                        <div
                          v-if="prize.disabled"
                          data-v-9ca7245c=""
                          class="locked"
                        ></div>
                        <div class="image">
                          <img :src="prize.img" alt="" />
                        </div>
                        <div class="text">{{ prize.text }}</div>
                        <svg
                          v-if="prize.disabled"
                          data-v-9ca7245c=""
                          width="16"
                          height="16"
                          viewBox="0 0 16 16"
                          fill="none"
                          xmlns="http://www.w3.org/2000/svg"
                          class="lock"
                        >
                          <path
                            data-v-9ca7245c=""
                            fill-rule="evenodd"
                            clip-rule="evenodd"
                            d="M7.99999 1.33325C10.025 1.33325 11.6667 2.97487 11.6667 4.99992V6.33325H14C14.3682 6.33325 14.6667 6.63173 14.6667 6.99992V13.9999C14.6667 14.3681 14.3682 14.6666 14 14.6666H1.99999C1.63181 14.6666 1.33333 14.3681 1.33333 13.9999V6.99992C1.33333 6.63173 1.63181 6.33325 1.99999 6.33325H4.33333V4.99992C4.33333 2.97487 5.97495 1.33325 7.99999 1.33325ZM8.33335 8.66667C8.51744 8.66667 8.66668 8.81591 8.66668 9V12C8.66668 12.1841 8.51744 12.3333 8.33335 12.3333H7.66668C7.48259 12.3333 7.33335 12.1841 7.33335 12V9C7.33335 8.81591 7.48259 8.66667 7.66668 8.66667H8.33335ZM5.66668 5C5.66668 3.71134 6.71135 2.66667 8.00001 2.66667C9.28868 2.66667 10.3333 3.71134 10.3333 5V6.33333H5.66668V5Z"
                            fill="#D25F00"
                          ></path>
                        </svg>
                      </div>
                    </template>
                  </gridPrize>
                </template>
              </gridRoll>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { gridRoll, gridStart, gridPrize } from "grid-roll";
import "grid-roll/dist/grid-roll.min.css";
export default {
  name: "App",
  data() {
    return {
      completeNumber: 0,
    };
  },
  computed: {
    prizes() {
      return [
        {
          id: 1,
          text: "66矿石",
          img: "https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/32ed6a7619934144882d841761b63d3c~tplv-k3u1fbpfcp-no-mark:0:0:0:0.awebp",
        },
        {
          id: 2,
          text: "随机限量徽章",
          img: "https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/71c68de6368548bd9bd6c8888542f911~tplv-k3u1fbpfcp-no-mark:0:0:0:0.awebp",
        },
        {
          id: 3,
          text: "掘金新款T恤",
          img: "https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/5bf91038a6384fc3927dee294a38006b~tplv-k3u1fbpfcp-no-mark:0:0:0:0.awebp",
        },
        {
          id: 4,
          text: "Bug",
          img: "https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/0a4ce25d48b8405cbf5444b6195928d4~tplv-k3u1fbpfcp-no-mark:0:0:0:0.awebp",
        },
        {
          id: 5,
          text:
            this.completeNumber >= 2
              ? "乐高海洋巨轮"
              : `再抽${2 - this.completeNumber}次解锁`,
          img: "https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/aabe49b0d5c741fa8d92ff94cd17cb90~tplv-k3u1fbpfcp-no-mark:0:0:0:0.awebp",
          disabled: this.completeNumber < 2,
        },
        {
          id: 6,
          text: "掘金限量桌垫",
          img: "https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/c78f363f41a741ffa11dcc8a92b72407~tplv-k3u1fbpfcp-no-mark:0:0:0:0.awebp",
        },
        {
          id: 7,
          text: "Yoyo抱枕",
          img: "https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/33f4d465a6a9462f9b1b19b3104c8f91~tplv-k3u1fbpfcp-no-mark:0:0:0:0.awebp",
        },
        {
          id: 8,
          text:
            this.completeNumber >= 3
              ? "Switch"
              : `再抽${3 - this.completeNumber}次解锁`,
          img: "https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/4decbd721b2b48098a1ecf879cfca677~tplv-k3u1fbpfcp-no-mark:0:0:0:0.awebp",
          disabled: this.completeNumber < 3,
        },
      ];
    },
  },
  components: {
    gridRoll,
    gridStart,
    gridPrize,
  },
  methods: {
    async handleLottery() {
      const value = 1;
      const b = await this.$refs.dial.startRoll(value);
      if (b) {
        alert(
          `🎉你抽到${this.prizes.find((prize) => prize.id === value).text}`
        );
        this.completeNumber++;
      } else {
        console.warn("稍安勿躁");
      }
    },
  },
};
</script>

<style lang="scss" scoped>
#app {
  .left_part {
    margin: 50px auto 0;
    width: 486px;
    .lottery {
      width: 100%;
      height: 396px;
      .turntable-box {
        background: #fadd95;
        box-shadow: inset 0 0 16px #ff9a2e;
        border-radius: 12px;
        box-sizing: border-box;
        position: relative;
        padding: 24px;
        width: 100%;
        height: 100%;
        .upper-border {
          top: 0;
        }
        .up-down {
          position: absolute;
          left: 8px;
          display: flex;
          align-items: center;
          height: 24px;
          width: calc(100% - 16px);
          justify-content: space-between;
          .left-border-dot {
            transform: translateX(-100%);
          }
          .right-border-dot {
            transform: translateX(100%);
          }
        }
        .vertex {
          background: #e37815;
        }
        .white {
          background: #fff7e8;
        }
        .dot {
          border-radius: 50%;
          box-sizing: border-box;
          width: 12px;
          height: 12px;
        }
        .border {
          border: 1.5px solid #fff7e8;
        }
        .lower-border {
          bottom: 0;
        }
        .left-border {
          left: 0;
          .vertex {
            visibility: hidden;
          }
        }
        .left-right {
          position: absolute;
          top: 8px;
          display: flex;
          align-items: center;
          width: 24px;
          height: calc(100% - 16px);
          justify-content: space-between;
          flex-direction: column;
        }
        .right-border {
          right: 0;
          .vertex {
            visibility: hidden;
          }
        }
      }
    }
  }
  .blocks {
    width: 100%;
    height: 100%;
    .item-container {
      width: 100%;
      height: 100%;
      background: #e37815;
      border-radius: 8px;
      padding: 18px;
      box-sizing: border-box;
      .item {
        width: 130px;
        height: 100px;
      }
      .lottery {
        background: #ffe6a6;
        box-shadow: inset 0 0 16px #ffa800;
        cursor: pointer;
      }
      .turntable-item {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        background: #fdf3f3;
        border-radius: 4px;
        position: relative;
        user-select: none;
        &.chosen {
          background: #ffcf8b;
        }
        .lock {
          position: absolute;
          width: 16px;
          height: 16px;
          top: 8px;
          right: 8px;
        }
        .lottery-text {
          font-size: 32px;
          line-height: 42px;
          font-weight: 600;
          color: #a74b00;
        }
        .image {
          height: 50px;
          width: 72px;
          display: flex;
          justify-content: center;
          align-items: center;
          img {
            max-width: 40px;
            max-height: 40px;
            height: 100%;
          }
        }
        .text {
          font-size: 14px;
          font-weight: 400;
          line-height: 22px;
          color: #d25f00;
          max-width: 100%;
          white-space: nowrap;
          overflow: hidden;
          text-overflow: ellipsis;
        }
      }
    }
  }
}
svg:not(:root) {
  overflow: hidden;
}
.locked {
  position: absolute;
  width: 100%;
  height: 100%;
  background: #fdf3f3;
  opacity: 0.7;
}
</style>
