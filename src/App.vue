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
              <gridRoll interval="6px">
                <template v-slot:button>
                  <gridStart>
                    <div class="turntable-item item lottery">
                      <div class="lottery-text">抽奖</div>
                      <div class="text">200矿石1次</div>
                    </div>
                  </gridStart>
                </template>
                <template v-slot:prize>
                  <gridPrize
                    v-for="prize in prizes"
                    :key="prize.id"
                    :pic="prize.id"
                  >
                    <div class="turntable-item item">
                      <div class="image">
                        <img :src="prize.img" alt="" />
                      </div>
                      <div class="text">{{ prize.text }}</div>
                    </div>
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
      prizes: [
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
          text: "再抽2次解锁",
          img: "https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/aabe49b0d5c741fa8d92ff94cd17cb90~tplv-k3u1fbpfcp-no-mark:0:0:0:0.awebp",
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
          text: "再抽3次解锁",
          img: "https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/4decbd721b2b48098a1ecf879cfca677~tplv-k3u1fbpfcp-no-mark:0:0:0:0.awebp",
        },
      ],
    };
  },
  components: {
    gridRoll,
    gridStart,
    gridPrize,
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
</style>
