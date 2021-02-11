<template>
    <div class="home">
        <b-container>
            <b-row>
                <b-col>
                    <div class="home_wrapper">
                        <h1 class="text-4xl text-center py-12">{{ $t('home.desc') }}</h1>
                        <div class="max-w-6xl container mx-auto grid grid-cols-6 pt-12 mb-12">
                            <!-- Login to wallet -->
                            <div
                                class="grid justify-items-center col-span-6 md:col-span-6 lg:col-span-3"
                            >
                                <router-link
                                    data-cy="access"
                                    to="/access"
                                    class="button_primary px-6"
                                >
                                    <div class="grid grid-cols-12 h-full max-w-md py-8">
                                        <div class="py-4 col-span-2 my-auto">
                                            <img
                                                class="icons"
                                                v-if="$root.theme === 'day'"
                                                src="@/assets/WalletWhite.svg"
                                                alt
                                            />
                                            <img
                                                v-else
                                                class="icons"
                                                src="@/assets/WalletBlack.svg"
                                                alt
                                            />
                                        </div>
                                        <div class="col-span-10 my-auto text-left px-6">
                                            <h2 class="font-bold text-md text-xl">Access Wallet</h2>
                                            <p class="pt-3 text-lg">
                                                Access your existing Avalanche wallet and select a
                                                network.
                                            </p>
                                        </div>
                                    </div>
                                </router-link>
                            </div>
                            <!-- Create Wallet -->
                            <div
                                class="grid justify-items-center col-span-6 md:col-span-6 lg:col-span-3"
                            >
                                <router-link
                                    data-cy="create"
                                    to="/create"
                                    class="button_secondary px-6"
                                >
                                    <div class="grid grid-cols-12 h-full max-w-md py-8">
                                        <div class="py-4 col-span-2 my-auto">
                                            <img
                                                class="icons"
                                                v-if="$root.theme === 'day'"
                                                src="@/assets/NewWalletWhite.svg"
                                                alt
                                            />
                                            <img
                                                v-else
                                                class="icons"
                                                src="@/assets/NewWalletWhite.svg"
                                                alt
                                            />
                                        </div>
                                        <div class="col-span-10 my-auto text-left px-6">
                                            <h2 class="font-bold text-md text-xl">
                                                Create New Wallet
                                            </h2>
                                            <p class="pt-3 text-lg">
                                                Create a new Avalanche wallet to send, receive and
                                                swap assets.
                                            </p>
                                        </div>
                                    </div>
                                </router-link>
                            </div>
                        </div>
                        <img class="vector mt-16" src="@/assets/tree-alt.svg" alt />
                    </div>
                    <div class="max-w-6xl"></div>
                </b-col>
            </b-row>
        </b-container>
    </div>
</template>

<script lang="ts">
import 'reflect-metadata'
import { Vue, Component, Prop } from 'vue-property-decorator'

@Component({
    name: 'home',
})
export default class Home extends Vue {}
</script>

<style scoped lang="scss">
@use "../main";

.vector {
    max-height: 250px;
}

.home {
    padding-top: 100px;
    /*background-color: #fff;*/
    display: flex;
    justify-content: center;
    align-items: flex-start;
    position: relative;

    a {
        margin: 10px;
        text-align: center;
        display: block;
    }

    .home_wrapper {
        display: flex;
        flex-direction: column;
        align-content: center;
        justify-content: center;

        .login_wrapper {
            margin-top: 60px;
            display: grid;
            grid-template-columns: 1fr 1fr;
            column-gap: main.$container-padding;

            .login_option {
                display: flex;
                flex-direction: column;
                border-radius: 2px;
                align-items: flex-start;
                justify-content: space-between;
                background-color: var(--bg-light);
                padding: 60px 90px main.$container-padding main.$container-padding;

                header {
                    margin-bottom: 60px;

                    h2 {
                        padding-top: main.$s-size;
                        font-family: 'DM Sans', sans-serif;
                        font-size: main.$s-size;
                        text-transform: uppercase;
                        color: var(--primary-color-light);
                    }

                    p {
                        margin-top: 10px !important;
                        font-size: main.$l-size;
                    }
                }

                a {
                    margin: 0;
                }
            }
        }
    }
}

/* ==========================================
   Nav
   ========================================== */

@include main.night-mode {
}
.logo {
    margin-bottom: 30px;
}

img.icons {
    max-height: 50px;
    object-fit: contain;
}

@include main.medium-device {
    .login_option {
        padding: 30px 40px !important;
        p {
            font-size: 1.4rem !important;
        }
    }
}

@include main.mobile-device {
    .auth {
        border-radius: 0;
        box-shadow: none;
    }

    .menu_option {
        padding: 5vh 12px;
    }
    .menu_option button {
        width: 100%;
        padding: 8px;
    }

    .imgcover {
        display: none;
    }

    .home {
        .home_wrapper {
            h1 {
                font-size: main.$xl-size-mobile;
            }

            .login_wrapper {
                grid-template-columns: none;
                display: flex;
                flex-direction: column;

                .login_option {
                    margin-bottom: main.$vertical-padding;
                    padding: 30px 15px;
                    align-items: center;

                    header {
                        display: flex;
                        flex-direction: column;
                        align-items: center;

                        margin-bottom: 30px;

                        img {
                            width: 40px;
                            height: 40px;
                        }

                        p {
                            margin-top: 10px !important;
                            font-size: main.$l-size-mobile;
                            text-align: center;
                        }
                    }

                    a {
                        margin: 0;
                    }
                }
            }
        }
    }
}

@media only screen and (max-width: 600px) {
}
</style>
