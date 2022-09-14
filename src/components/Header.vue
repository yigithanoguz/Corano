<template>
  <div class="header">
    <div class="container">
      <div class="left">
        <div class="logo">
          <img src="../assets/logo.png" alt="Logo" />
        </div>
        <div class="link">
          <ul>
            <li>
              <a class="selected"
                >Home <i class="bi bi-chevron-down"></i>
                <ul class="home__ul">
                  <li>
                    <a>Home Version 01</a>
                  </li>
                  <li>
                    <a>Home Version 02</a>
                  </li>
                  <li>
                    <a>Home Version 03</a>
                  </li>
                  <li>
                    <a>Home Version 04</a>
                  </li>
                  <li>
                    <a>Home Version 05</a>
                  </li>
                  <li>
                    <a>Home Version 06</a>
                  </li>
                </ul>
              </a>
            </li>
            <li>
              <a
                >Pages <i class="bi bi-chevron-down"></i>
                <ul class="pages__ul">
                  <div class="columns">
                    <li>
                      <span class="title">Column 01</span>
                      <ul>
                        <li><a>Shop Grid Left Sidebar</a></li>
                        <li><a>Shop Grid Right Sidebar</a></li>
                        <li><a>Shop List Left Sidebar</a></li>
                        <li><a>Shop List Right Sidebar</a></li>
                      </ul>
                    </li>
                    <li>
                      <span class="title">Column 02</span>
                      <ul>
                        <li><a>Shop Grid Left Sidebar</a></li>
                        <li><a>Shop Grid Right Sidebar</a></li>
                        <li><a>Shop List Left Sidebar</a></li>
                        <li><a>Shop List Right Sidebar</a></li>
                      </ul>
                    </li>
                    <li>
                      <span class="title">Column 03</span>
                      <ul>
                        <li><a>Shop Grid Left Sidebar</a></li>
                        <li><a>Shop Grid Right Sidebar</a></li>
                        <li><a>Shop List Left Sidebar</a></li>
                        <li><a>Shop List Right Sidebar</a></li>
                      </ul>
                    </li>
                    <li>
                      <span class="title">Column 04</span>
                      <ul>
                        <li><a>Shop Grid Left Sidebar</a></li>
                        <li><a>Shop Grid Right Sidebar</a></li>
                        <li><a>Shop List Left Sidebar</a></li>
                        <li><a>Shop List Right Sidebar</a></li>
                      </ul>
                    </li>
                  </div>
                  <div class="images">
                    <img
                      src="https://htmldemo.net/corano/corano/assets/img/banner/img1-static-menu.jpg"
                      alt="..."
                    />
                    <img
                      src="https://htmldemo.net/corano/corano/assets/img/banner/img2-static-menu.jpg"
                      alt="..."
                    />
                  </div>
                </ul>
              </a>
            </li>
            <li>
              <a
                >Shop <i class="bi bi-chevron-down"></i>
                <ul class="shop__ul">
                  <li>
                    <a>Shop Layout</a>
                    <i class="bi bi-chevron-right"></i>
                    <ul class="shop__ul-ul">
                      <li>
                        <a>Shop Grid Sidebar</a>
                      </li>
                      <li>
                        <a>Shop Grid Sidebar</a>
                      </li>
                      <li>
                        <a>Shop Grid Sidebar</a>
                      </li>
                    </ul>
                  </li>
                  <li>
                    <a>Shop Layout</a>
                    <i class="bi bi-chevron-right"></i>
                    <ul class="shop__ul-ul">
                      <li>
                        <a>Shop Grid Sidebar</a>
                      </li>
                      <li>
                        <a>Shop Grid Sidebar</a>
                      </li>
                      <li>
                        <a>Shop Grid Sidebar</a>
                      </li>
                    </ul>
                  </li>
                  <li>
                    <a>Shop Layout</a>
                    <i class="bi bi-chevron-right"></i>
                    <ul class="shop__ul-ul">
                      <li>
                        <a>Shop Grid Sidebar</a>
                      </li>
                      <li>
                        <a>Shop Grid Sidebar</a>
                      </li>
                      <li>
                        <a>Shop Grid Sidebar</a>
                      </li>
                    </ul>
                  </li>
                </ul>
              </a>
            </li>
            <li>
              <a
                >Blog <i class="bi bi-chevron-down"></i>
                <ul class="blog__ul">
                  <li>
                    <a>Blog Left Sidebar 01</a>
                  </li>
                  <li>
                    <a>Blog Left Sidebar 02</a>
                  </li>
                  <li>
                    <a>Blog Left Sidebar 03</a>
                  </li>
                  <li>
                    <a>Blog Left Sidebar 04</a>
                  </li>
                  <li>
                    <a>Blog Left Sidebar 05</a>
                  </li>
                  <li>
                    <a>Blog Left Sidebar 06</a>
                  </li>
                </ul>
              </a>
            </li>
            <li>
              <a>Contact Us</a>
            </li>
          </ul>
        </div>
      </div>
      <div class="right">
        <div class="buttons">
          <ul>
            <li>
              <a
                ><i class="bi bi-search" @click="searchInputShow"></i>
                <div class="input-search" v-show="searchInput">
                  <i class="bi bi-search"></i>
                  <input
                    type="text"
                    placeholder="Search entire store hire"
                    v-model="searchInputText"
                    :class="{ active: searchInputText != '' }"
                  />
                </div>
              </a>
            </li>
            <li>
              <a
                ><i class="bi bi-person-circle"></i>
                <ul>
                  <li><a>Login</a></li>
                  <li><a>Register</a></li>
                  <li><a>My Account</a></li>
                </ul>
              </a>
            </li>
            <li>
              <a
                ><i class="bi bi-suit-heart"></i>
                <span class="count">0</span>
              </a>
            </li>
            <li>
              <a><i class="bi bi-bag"></i> <span class="count">2</span></a>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Header",
  data() {
    return {
      searchInput: false,
      searchInputText: "",
    };
  },
  methods: {
    searchInputShow() {
      this.searchInput = !this.searchInput;
    },
  },
};
</script>

<style lang="scss" scoped>
$color-bg: #f4f4f4;
$color-text: #555555;
$color-white: #fff;
$color-black: #000;
$color-gold: #c29958;
$color-border: #efefef;
$color-bg-search: #f7f7f7;
$color-border-search: #ddd;

.header {
  height: 100px;
  z-index: 5;
  background-color: $color-white;
  border-bottom: solid 1px $color-border;
  &.position-sticky {
    position: sticky;
    height: 65px;
    top: 0;
    box-shadow: rgba(99, 99, 99, 0.2) 0px 2px 8px 0px;
    ul {
      top: 64px !important;
    }
  }
  .container {
    height: 100%;
    width: 75%;
    margin: 0 auto;
    padding: 0 10px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    .left {
      height: 100%;
      display: flex;
      gap: 80px;
      .logo {
        align-self: center;
        img {
          height: 33px;
          width: 112px;
          cursor: pointer;
        }
      }
      .link {
        height: 100%;
        font-size: 0.95rem;
        z-index: 3;
        > ul {
          height: 100%;
          display: flex;
          gap: 30px;
          > li {
            height: 100%;
            > a {
              height: 100%;
              display: flex;
              align-items: center;
              gap: 5px;
              transition: color ease 300ms;
              position: relative;
              cursor: pointer;
              &.selected {
                color: $color-gold;
              }
              i.bi {
                font-size: 0.7rem;
              }
              &:hover {
                color: $color-gold;
                .home__ul {
                  display: flex;
                }
                .pages__ul {
                  display: block;
                }
                .blog__ul {
                  display: flex;
                }
                .shop__ul {
                  display: flex;
                }
              }
              .shop__ul {
                display: none;
                width: 220px;
                flex-direction: column;
                color: $color-text;
                background-color: $color-white;
                position: absolute;
                top: 99px;
                left: 0;
                border: solid 1px $color-border;
                li {
                  position: relative;
                  border-bottom: $color-border 1px dotted;
                  &:hover {
                    color: $color-gold;
                    .shop__ul-ul {
                      display: flex;
                    }
                  }
                  i.bi {
                    position: absolute;
                    top: 15px;
                    right: 15px;
                  }
                  .shop__ul-ul {
                    display: none;
                    width: 220px;
                    flex-direction: column;
                    color: $color-text;
                    background-color: $color-white;
                    position: absolute;
                    top: 0;
                    left: 218px;
                    border: solid 1px $color-border;
                    li {
                      position: relative;
                      border-bottom: $color-border 1px dotted;
                      a {
                        height: 45px;
                        width: 100%;
                        padding: 0 20px;
                        display: flex;
                        align-items: center;

                        transition: 400ms all;
                        &:before {
                          content: "__";
                          position: absolute;
                          top: 5px;
                          left: 21px;
                          opacity: 0;
                          transition: opacity 400ms;
                          font-weight: bold;
                        }

                        &:hover {
                          color: $color-gold;
                          margin-left: 18px;
                          &:before {
                            opacity: 1;
                          }
                        }
                      }
                    }
                  }
                  a {
                    height: 45px;
                    width: 100%;
                    padding: 0 20px;
                    display: flex;
                    align-items: center;

                    transition: 400ms all;
                    &:before {
                      content: "__";
                      position: absolute;
                      top: 5px;
                      left: 21px;
                      opacity: 0;
                      transition: opacity 400ms;
                      font-weight: bold;
                    }

                    &:hover {
                      margin-left: 18px;
                      &:before {
                        opacity: 1;
                      }
                    }
                  }
                }
              }
              .pages__ul {
                width: 75vw;
                padding: 40px 30px;
                display: none;
                background-color: $color-white;
                color: $color-text;
                position: absolute;
                top: 99px;
                left: -280px;
                border: solid 1px $color-border;
                .columns {
                  display: grid;
                  grid-template-columns: repeat(4, 1fr);
                  text-align: left;
                  > li {
                    .title {
                      padding-bottom: 10px;
                      font-size: 1rem;
                      font-weight: bold;
                      color: $color-black;
                      // border-bottom: solid 2px $color-border;
                      position: relative;
                      cursor: text;
                      &:before {
                        content: "";
                        width: 50%;
                        position: absolute;
                        top: 30px;
                        left: 0;
                        border-bottom: solid 2px $color-gold;
                        z-index: 1;
                      }
                      &:after {
                        content: "";
                        width: 100%;
                        position: absolute;
                        top: 30px;
                        left: 0;
                        border-bottom: solid 2px $color-border;
                      }
                    }
                    ul {
                      margin-top: 25px;
                      font-size: 0.85rem;
                      li {
                        position: relative;
                        a {
                          height: 40px;
                          display: flex;
                          align-items: center;
                          width: 100%;
                          cursor: pointer;
                          transition: 400ms all;
                          &:before {
                            content: "__";
                            position: absolute;
                            top: 6px;
                            left: 0px;
                            opacity: 0;
                            transition: opacity 400ms;
                            font-weight: bold;
                          }

                          &:hover {
                            color: $color-gold;
                            margin-left: 18px;
                            &:before {
                              opacity: 1;
                            }
                          }
                        }
                      }
                    }
                  }
                }
                .images {
                  display: flex;
                  gap: 30px;
                  margin-top: 20px;
                  img {
                    flex-basis: 50%;
                  }
                }
              }
              .home__ul {
                display: none;
                width: 220px;
                flex-direction: column;
                color: $color-text;
                background-color: $color-white;
                position: absolute;
                top: 99px;
                left: 0;
                border: solid 1px $color-border;
                li {
                  position: relative;
                  border-bottom: $color-border 1px dotted;
                  a {
                    height: 45px;
                    width: 100%;
                    padding: 0 20px;
                    display: flex;
                    align-items: center;

                    transition: 400ms all;
                    &:before {
                      content: "__";
                      position: absolute;
                      top: 5px;
                      left: 21px;
                      opacity: 0;
                      transition: opacity 400ms;
                      font-weight: bold;
                    }

                    &:hover {
                      color: $color-gold;
                      margin-left: 18px;
                      &:before {
                        opacity: 1;
                      }
                    }
                  }
                }
              }
              .blog__ul {
                display: none;
                width: 220px;
                flex-direction: column;
                color: $color-text;
                background-color: $color-white;
                position: absolute;
                top: 99px;
                left: 0;
                border: solid 1px $color-border;
                li {
                  position: relative;
                  border-bottom: $color-border 1px dotted;
                  a {
                    height: 45px;
                    width: 100%;
                    padding: 0 20px;
                    display: flex;
                    align-items: center;

                    transition: 400ms all;
                    &:before {
                      content: "__";
                      position: absolute;
                      top: 5px;
                      left: 21px;
                      opacity: 0;
                      transition: opacity 400ms;
                      font-weight: bold;
                    }

                    &:hover {
                      color: $color-gold;
                      margin-left: 18px;
                      &:before {
                        opacity: 1;
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    .right {
      height: 100%;
      .buttons {
        height: 100%;
        > ul {
          display: flex;
          gap: 30px;
          height: 100%;
          > li {
            height: 100%;
            > a {
              height: 100%;
              display: flex;
              align-items: center;
              position: relative;
              .count {
                height: 18px;
                width: 18px;
                display: flex;
                justify-content: center;
                align-items: center;
                position: absolute;
                top: 30px;
                right: -7.5px;
                background-color: $color-gold;
                border-radius: 50%;
                font-size: 0.7rem;
                color: $color-white;
              }
              > i.bi {
                font-size: 1.4rem;
                transition: color ease 300ms;
                cursor: pointer;
                &:hover {
                  color: $color-gold;
                }
              }
              .input-search {
                position: absolute;
                top: 70px;
                right: 0px;

                &:hover {
                  i.bi {
                    color: $color-gold;
                  }
                }
                i.bi {
                  position: absolute;
                  top: 10px;
                  left: 20px;
                  font-size: 1.1rem;
                  transition: 300ms;
                  cursor: pointer;
                }
                input {
                  height: 44px;
                  width: 300px;
                  padding: 10px 40px 10px 50px;
                  background-color: $color-bg-search;
                  font-size: 0.75rem;
                  letter-spacing: 0.5px;
                  border: solid 1px $color-border-search;
                  border-radius: 30px;
                  outline: none;
                  &.active {
                    font-size: 0.85rem;
                    letter-spacing: 0px;
                  }
                }
              }
              ul {
                display: none;
                height: auto;
                width: 150px;
                padding: 30px 20px;
                position: absolute;
                top: 65px;
                right: 0;
                opacity: 1;
                font-size: 0.8rem;
                animation-name: slide;
                animation-duration: 500ms;
                background-color: $color-white;
                color: $color-text;
                border: solid 1px $color-border;
                z-index: 3;
              }
              &:hover {
                ul {
                  display: flex;
                  flex-direction: column;
                  align-items: flex-start;
                  gap: 15px;
                  @keyframes slide {
                    from {
                      top: 115px;
                      opacity: 0;
                    }
                    to {
                      top: 65px;
                      opacity: 1;
                    }
                  }
                  li {
                    transition: color 300ms;
                    cursor: pointer;
                    &:hover {
                      color: $color-gold;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
}
</style>
