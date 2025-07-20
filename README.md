<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <link rel="apple-touch-icon" sizes="180x180" href="Desktop/WechatIMG22.jpg">
    <link rel="icon" type="image/png" sizes="32x32" href="Desktop/WechatIMG19.jpg">
    <link rel="icon" type="image/png" sizes="16x16" href="Desktop/WechatIMG28.jpg">
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Coserbox - 一站式Cosplay服务平台</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdn.jsdelivr.net/npm/font-awesome@4.7.0/css/font-awesome.min.css" rel="stylesheet">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        primary: '#FF6AD5', // 亮粉色
                        secondary: '#4DEEEA', // 天蓝色
                        dark: '#2D2B55', // 深紫色
                        light: '#FFF9E6', // 米白色
                        accent: '#FFD166', // 亮黄色
                        neonPink: '#FF2E93',
                        neonBlue: '#00B4D8',
                        neonGreen: '#06D6A0'
                    },
                    fontFamily: {
                        sans: ['"Comic Sans MS"', '"Bubblegum Sans"', 'cursive', 'sans-serif'],
                    },
                    borderRadius: {
                        'xl': '1rem',
                        '2xl': '1.5rem',
                        '3xl': '2rem',
                        '4xl': '2.5rem',
                    },
                    boxShadow: {
                        'anime': '0 10px 25px -5px rgba(255, 106, 213, 0.4), 0 8px 10px -6px rgba(77, 238, 234, 0.3)',
                        'anime-hover': '0 20px 35px -10px rgba(255, 106, 213, 0.6), 0 10px 15px -5px rgba(77, 238, 234, 0.4)'
                    }
                }
            }
        }
    </script>
    <style type="text/tailwindcss">
        @layer utilities {
            .content-auto {
                content-visibility: auto;
            }
            .text-shadow {
                text-shadow: 2px 2px 0px rgba(0,0,0,0.2);
            }
            .text-shadow-anime {
                text-shadow: 0 0 5px rgba(255, 106, 213, 0.7), 0 0 10px rgba(77, 238, 234, 0.5);
            }
            .border-anime {
                border-image: linear-gradient(to right, #FF6AD5, #4DEEEA) 1;
            }
            .bg-anime-pattern {
                background-image: radial-gradient(circle at 10% 20%, rgba(255, 106, 213, 0.1) 0%, rgba(77, 238, 234, 0.1) 90%);
            }
            .animate-float {
                animation: float 6s ease-in-out infinite;
            }
            @keyframes float {
                0% { transform: translateY(0px); }
                50% { transform: translateY(-15px); }
                100% { transform: translateY(0px); }
            }
            .animate-pulse-slow {
                animation: pulse 4s cubic-bezier(0.4, 0, 0.6, 1) infinite;
            }
            .cartoon-border {
                border-image: repeating-linear-gradient(45deg, #FF6AD5, #FF6AD5 10px, #4DEEEA 10px, #4DEEEA 20px) 1;
            }
            .star {
                position: absolute;
                width: 10px;
                height: 10px;
                background: #FFD700;
                clip-path: polygon(50% 0%, 61% 35%, 98% 35%, 68% 57%, 79% 91%, 50% 70%, 21% 91%, 32% 57%, 2% 35%, 39% 35%);
            }
        }
    </style>
</head>
<body class="bg-light text-dark antialiased">
    <!-- 导航栏 -->
    <header id="navbar" class="fixed w-full top-0 z-50 transition-all duration-300 bg-white/90 backdrop-blur-sm shadow-sm">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-16 md:h-20">
                <!-- Logo -->
                <div class="flex items-center">
                    <a href="#" class="flex items-center">
                        <span class="text-primary text-2xl font-bold">Coserbox</span>
                    </a>
                </div>

                <!-- 桌面导航 -->
                <nav class="hidden md:flex space-x-8">
                    <a href="#home" class="text-dark hover:text-primary font-medium transition-custom">首页</a>
                    <a href="#buy" class="text-dark hover:text-primary font-medium transition-custom">二手购买</a>
                    <a href="#renovation" class="text-dark hover:text-primary font-medium transition-custom">服装翻新</a>
                    <a href="#rent" class="text-dark hover:text-primary font-medium transition-custom">服装租赁</a>
                    <a href="#collaborate" class="text-dark hover:text-primary font-medium transition-custom">专业合作</a>
                    <a href="vip.html" class="text-primary hover:text-primary font-medium transition-custom">VIP会员</a>
                    <a href="#contact" class="text-dark hover:text-primary font-medium transition-custom">联系我们</a>
                </nav>

                <!-- 预约按钮 -->
                <div class="hidden md:block">
                    <a href="#booking" class="bg-primary hover:bg-primary/90 text-white px-5 py-2 rounded-full font-medium transition-custom shadow-md hover:shadow-lg">
                        立即预约
                    </a>
                </div>

                <!-- 移动端菜单按钮 -->
                <div class="md:hidden">
                    <button id="menu-toggle" class="text-dark hover:text-primary focus:outline-none">
                        <i class="fa fa-bars text-xl"></i>
                    </button>
                </div>
            </div>
        </div>

        <!-- 移动端导航菜单 -->
        <div id="mobile-menu" class="hidden md:hidden bg-white shadow-lg absolute w-full">
            <div class="container mx-auto px-4 py-3 space-y-3">
                <a href="#home" class="block text-dark hover:text-primary font-medium py-2 transition-custom">首页</a>
                <a href="#buy" class="block text-dark hover:text-primary font-medium py-2 transition-custom">二手购买</a>
                <a href="#renovation" class="block text-dark hover:text-primary font-medium py-2 transition-custom">服装翻新</a>
                <a href="#rent" class="block text-dark hover:text-primary font-medium py-2 transition-custom">服装租赁</a>
                <a href="#collaborate" class="block text-dark hover:text-primary font-medium py-2 transition-custom">专业合作</a>
                <a href="vip.html" class="block text-primary hover:text-primary font-medium py-2 transition-custom">VIP会员</a>
                <a href="#contact" class="block text-dark hover:text-primary font-medium py-2 transition-custom">联系我们</a>
                <a href="#booking" class="block bg-primary hover:bg-primary/90 text-white px-5 py-2 rounded-full font-medium text-center transition-custom shadow-md hover:shadow-lg">
                    立即预约
                </a>
            </div>
        </div>
    </header>

    <!-- 英雄区域 -->
    <section id="home" class="pt-24 md:pt-32 pb-16 md:pb-24 bg-gradient-to-br from-primary/5 to-secondary/5">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex flex-col md:flex-row items-center">
                <div class="md:w-1/2 mb-10 md:mb-0">
                    <h1 class="text-[clamp(2rem,5vw,3.5rem)] font-bold leading-tight text-dark mb-4">
                        一站式<span class="text-primary">Cosplay</span>服务平台
                    </h1>
                    <p class="text-lg md:text-xl text-gray-600 mb-8 max-w-lg">
                        从二手服装购买、专业翻新到租赁服务，以及与顶级化妆师和摄影师的合作，为您打造完美的Cosplay体验。
                    </p>
                    <div class="flex flex-col sm:flex-row space-y-4 sm:space-y-0 sm:space-x-4">
                        <a href="#rent" class="bg-primary hover:bg-primary/90 text-white px-8 py-3 rounded-full font-medium text-center transition-custom shadow-lg hover:shadow-xl">
                            浏览服装
                        </a>
                        <a href="#collaborate" class="bg-white hover:bg-gray-50 text-primary border-2 border-primary px-8 py-3 rounded-full font-medium text-center transition-custom shadow-md hover:shadow-lg">
                            专业合作
                        </a>
                    </div>
                </div>
                <div class="md:w-1/2 relative">
                    <div class="relative z-10 rounded-4xl overflow-hidden shadow-anime transform transition-transform hover:scale-[1.03] duration-700 animate-float">
                        <img src="Desktop/WechatIMG22_副本.jpg" alt="动漫风格Cosplay展示" class="w-full h-auto">
                    </div>
                    <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-full h-full bg-gradient-to-r from-neonPink/30 to-neonBlue/30 rounded-full blur-3xl -z-10 opacity-70 animate-pulse-slow"></div>
                    <div class="absolute -bottom-6 -right-6 bg-light p-4 rounded-3xl shadow-anime rotate-3">
                        <div class="text-yellow-400 flex text-xl">
                            <i class="fa fa-star"></i>
                            <i class="fa fa-star"></i>
                            <i class="fa fa-star"></i>
                            <i class="fa fa-star"></i>
                            <i class="fa fa-star"></i>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 服务特点 -->
    <section class="py-16 md:py-24 bg-white">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-16">
                <h2 class="text-[clamp(1.8rem,4vw,2.5rem)] font-bold text-dark mb-4">我们的核心服务</h2>
                <p class="text-lg text-gray-600 max-w-2xl mx-auto">提供从服装到造型的全方位Cosplay解决方案，让您的创意轻松实现</p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
                <!-- 服务卡片1 -->
                <div class="bg-white rounded-xl shadow-lg p-6 transition-custom hover:shadow-xl hover:-translate-y-1 border border-gray-100">
                    <div class="w-14 h-14 bg-primary/10 rounded-full flex items-center justify-center mb-5">
                        <i class="fa fa-shopping-bag text-primary text-2xl"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-3 text-dark">二手服装购买</h3>
                    <p class="text-gray-600">高品质二手Cosplay服装，经过严格筛选和消毒处理，性价比之选。</p>
                </div>

                <!-- 服务卡片2 -->
                <div class="bg-white rounded-xl shadow-lg p-6 transition-custom hover:shadow-xl hover:-translate-y-1 border border-gray-100">
                    <div class="w-14 h-14 bg-secondary/10 rounded-full flex items-center justify-center mb-5">
                        <i class="fa fa-scissors text-secondary text-2xl"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-3 text-dark">专业服装翻新</h3>
                    <p class="text-gray-600">专业团队进行服装清洗、修补和改造，让旧服装焕发新生。</p>
                </div>

                <!-- 服务卡片3 -->
                <div class="bg-white rounded-xl shadow-lg p-6 transition-custom hover:shadow-xl hover:-translate-y-1 border border-gray-100">
                    <div class="w-14 h-14 bg-accent/10 rounded-full flex items-center justify-center mb-5">
                        <i class="fa fa-calendar-check-o text-accent text-2xl"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-3 text-dark">服装租赁服务</h3>
                    <p class="text-gray-600">多样化的服装租赁选择，灵活的租期和配送方式，满足不同需求。</p>
                </div>

                <!-- 服务卡片4 -->
                <div class="bg-white rounded-xl shadow-lg p-6 transition-custom hover:shadow-xl hover:-translate-y-1 border border-gray-100">
                    <div class="w-14 h-14 bg-primary/10 rounded-full flex items-center justify-center mb-5">
                        <i class="fa fa-users text-primary text-2xl"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-3 text-dark">专业团队合作</h3>
                    <p class="text-gray-600">与资深化妆师和摄影师合作，提供一站式造型和拍摄服务。</p>
                </div>
            </div>
        </div>
    </section>

    <!-- 业务模式介绍 -->
    <section class="py-16 md:py-24 bg-anime-pattern">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-16">
                <h2 class="text-[clamp(1.8rem,4vw,2.5rem)] font-bold text-dark mb-4">次元衣仓：二手Cos服的现实生存逻辑</h2>
                <p class="text-lg text-gray-600 max-w-2xl mx-auto">解决Cos圈"回收难、翻新贵、租不掉"的三大痛点</p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 gap-12 mb-16">
                <!-- 产品部分 -->
                <div class="bg-white rounded-xl shadow-lg p-8 transition-custom hover:shadow-anime">
                    <h3 class="text-2xl font-bold mb-6 text-primary flex items-center">
                        <i class="fa fa-cube mr-3"></i>产品：CoserBox体验极致轻松变身
                    </h3>
                    <ul class="space-y-4">
                        <li class="flex items-start">
                            <i class="fa fa-check-circle text-accent mt-1 mr-3"></i>
                            <div>
                                <span class="font-bold">流程：</span>
                                <span>聚焦经典二次元IP(动漫、游戏)，加上专业翻新服务，提供二手Cos服租赁服务，满足用户需求。</span>
                            </div>
                        </li>
                        <li class="flex items-start">
                            <i class="fa fa-check-circle text-accent mt-1 mr-3"></i>
                            <div>
                                <span class="font-bold">回收服装：</span>
                                <span>月回收50件，翻新标准化，成本120元/套，72小时内交付。</span>
                            </div>
                        </li>
                        <li class="flex items-start">
                            <i class="fa fa-check-circle text-accent mt-1 mr-3"></i>
                            <div>
                                <span class="font-bold">数字化：</span>
                                <span>小程序一键操作，服装实时查看+预约翻新案例库展示"600元回收→660元翻新->120日租"，让用户轻松租赁，省去复杂计算。</span>
                            </div>
                        </li>
                        <li class="flex items-start">
                            <i class="fa fa-check-circle text-accent mt-1 mr-3"></i>
                            <div>
                                <span class="font-bold">布局：</span>
                                <span>全国范围内提供回收、翻新、出租，周边卡片只推Top10热门IP，减少库存积压，提升市场需求。</span>
                            </div>
                        </li>
                    </ul>
                </div>

                <!-- 盈利部分 -->
                <div class="bg-white rounded-xl shadow-lg p-8 transition-custom hover:shadow-anime">
                    <h3 class="text-2xl font-bold mb-6 text-secondary flex items-center">
                    <i class="fa fa-line-chart mr-3"></i>盈利：微利循环，先活下来
                </h3>
                <ul class="space-y-4">
                    <li class="flex items-start">
                        <i class="fa fa-check-circle text-accent mt-1 mr-3"></i>
                        <div>
                            <span class="font-bold">采购和翻新成本：</span>
                            <span>每件衣服采购成本600元，翻新成本120元，总成本720元</span>
                        </div>
                    </li>
                    <li class="flex items-start">
                        <i class="fa fa-check-circle text-accent mt-1 mr-3"></i>
                        <div>
                            <span class="font-bold">租赁收入：</span>
                            <span>每件衣服可租10次，每次租赁收费120元，年收入1,200元</span>
                        </div>
                    </li>
                    <li class="flex items-start">
                        <i class="fa fa-check-circle text-accent mt-1 mr-3"></i>
                        <div>
                            <span class="font-bold">毛利润：</span>
                            <span>每件衣服毛利润=1,200元-720元=480元</span>
                        </div>
                    </li>
                    <li class="flex items-start">
                        <i class="fa fa-check-circle text-accent mt-1 mr-3"></i>
                        <div>
                            <span class="font-bold">规模效应：</span>
                            <span>1,250件库存的毛利润总额=480元×1,250件=600,000元</span>
                        </div>
                    </li>
                    <li class="flex items-start">
                        <i class="fa fa-check-circle text-accent mt-1 mr-3"></i>
                        <div>
                            <span class="font-bold">运营费用：</span>
                            <span>仓储、物流和平台维护等费用约300,000元</span>
                        </div>
                    </li>
                    <li class="flex items-start">
                        <i class="fa fa-check-circle text-accent mt-1 mr-3"></i>
                        <div>
                            <span class="font-bold">总成本：</span>
                            <span>采购和翻新成本720元×1,250件 + 运营费用300,000元 = 1,200,000元</span>
                        </div>
                    </li>
                    <li class="flex items-start">
                        <i class="fa fa-check-circle text-accent mt-1 mr-3"></i>
                        <div>
                            <span class="font-bold">净利润：</span>
                            <span>总收入1,500,000元 - 总成本1,200,000元 = 300,000元</span>
                        </div>
                    </li>
                </ul>
                        <li class="flex items-start">
                            <i class="fa fa-check-circle text-accent mt-1 mr-3"></i>
                            <div>
                                <span class="font-bold">成本锚点：</span>
                                <span>120㎡仓库月租2160元，覆盖存储+办公，压低成本。</span>
                            </div>
                        </li>
                    </ul>
                </div>
            </div>

            <div class="bg-dark text-white p-8 rounded-2xl text-center max-w-4xl mx-auto">
                <p class="text-lg mb-4">现实是：二手生意赚的是"周转钱"。我们瞄准成都3万活跃Coser里的1%（300人）</p>
                <p class="text-xl font-bold">靠聚焦刚需、砍成本、轻运营，先活下来，再谈扩张。这才是二手Cos服的真实机会。</p>
            </div>
        </div>
    </section>

    <!-- 二手购买区域 -->
    <section id="buy" class="py-16 md:py-24 bg-gray-50">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex flex-col md:flex-row items-center gap-12">
                <div class="md:w-1/2">
                    <h2 class="text-[clamp(1.8rem,4vw,2.5rem)] font-bold text-dark mb-6">二手Cos服装购买</h2>
                    <p class="text-lg text-gray-600 mb-6">
                        我们精心挑选高品质的二手Cosplay服装，每件都经过严格的质量检查和专业消毒处理。购买二手服装不仅经济实惠，还能为环保事业贡献一份力量。
                    </p>
                    <ul class="space-y-4 mb-8">
                        <li class="flex items-start">
                            <i class="fa fa-check-circle text-accent mt-1 mr-3"></i>
                            <span>每件服装均经过专业清洗和消毒处理</span>
                        </li>
                        <li class="flex items-start">
                            <i class="fa fa-check-circle text-accent mt-1 mr-3"></i>
                            <span>详细的尺寸信息和实物拍摄，所见即所得</span>
                        </li>
                        <li class="flex items-start">
                            <i class="fa fa-check-circle text-accent mt-1 mr-3"></i>
                            <span>7天无理由退换，购物无忧</span>
                        </li>
                        <li class="flex items-start">
                            <i class="fa fa-check-circle text-accent mt-1 mr-3"></i>
                            <span>购买满3件可享受免费翻新服务一次</span>
                        </li>
                    </ul>
                    <a href="#" class="inline-block bg-primary hover:bg-primary/90 text-white px-6 py-3 rounded-full font-medium transition-custom shadow-md hover:shadow-lg">
                        浏览二手服装
                    </a>
                </div>
                <div class="md:w-1/2 grid grid-cols-2 gap-4">
                    <div class="rounded-xl overflow-hidden shadow-lg transform rotate-3 transition-custom hover:rotate-0 duration-300">
                        <img src="Desktop/WechatIMG16.jpg" alt="二手Cos服装展示" class="w-full h-auto">}
                    </div>
                    <div class="rounded-xl overflow-hidden shadow-lg transform -rotate-2 transition-custom hover:rotate-0 duration-300 mt-8">
                        <img src="Desktop/WechatIMG34.jpg" alt="二手Cos服装展示" class="w-full h-auto">
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 服装翻新区域 -->
    <section id="renovation" class="py-16 md:py-24 bg-white">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex flex-col md:flex-row-reverse items-center gap-12">
                <div class="md:w-1/2">
                    <h2 class="text-[clamp(1.8rem,4vw,2.5rem)] font-bold text-dark mb-6">专业服装翻新服务</h2>
                    <p class="text-lg text-gray-600 mb-6">
                        无论您是购买了二手服装需要修复，还是想让自己的旧服装焕然一新，我们的专业团队都能满足您的需求。从简单的修补到复杂的改造，让您的服装重获新生。
                    </p>
                    <div class="grid grid-cols-2 gap-4 mb-8">
                        <div class="bg-gray-50 p-4 rounded-lg">
                            <h4 class="font-bold mb-2 flex items-center">
                                <i class="fa fa-tint text-primary mr-2"></i>专业清洗
                            </h4>
                            <p class="text-sm text-gray-600">去除顽固污渍，恢复服装原色</p>
                        </div>
                        <div class="bg-gray-50 p-4 rounded-lg">
                            <h4 class="font-bold mb-2 flex items-center">
                                <i class="fa fa-thread text-primary mr-2"></i>破损修补
                            </h4>
                            <p class="text-sm text-gray-600">专业缝补技术，无痕修复破损处</p>
                        </div>
                        <div class="bg-gray-50 p-4 rounded-lg">
                            <h4 class="font-bold mb-2 flex items-center">
                                <i class="fa fa-paint-brush text-primary mr-2"></i>重新上色
                            </h4>
                            <p class="text-sm text-gray-600">专业染色技术，恢复鲜艳色彩</p>
                        </div>
                        <div class="bg-gray-50 p-4 rounded-lg">
                            <h4 class="font-bold mb-2 flex items-center">
                                <i class="fa fa-magic text-primary mr-2"></i>创意改造
                            </h4>
                            <p class="text-sm text-gray-600">根据需求进行个性化改造升级</p>
                        </div>
                    </div>
                    <a href="#" class="inline-block bg-secondary hover:bg-secondary/90 text-white px-6 py-3 rounded-full font-medium transition-custom shadow-md hover:shadow-lg">
                        了解翻新流程
                    </a>
                </div>
                <div class="md:w-1/2">
                    <div class="relative">
                        <img src="Desktop/WechatIMG27.jpg" alt="服装翻新服务" class="w-full h-auto rounded-xl shadow-xl">
                        <div class="absolute -bottom-6 -left-6 bg-white p-4 rounded-lg shadow-lg max-w-xs">
                            <div class="flex items-center mb-2">
                                <div class="text-yellow-400 flex">
                                    <i class="fa fa-star"></i>
                                    <i class="fa fa-star"></i>
                                    <i class="fa fa-star"></i>
                                    <i class="fa fa-star"></i>
                                    <i class="fa fa-star"></i>
                                </div>
                                <span class="ml-2 font-bold">5.0</span>
                            </div>
                            <p class="text-sm italic">"翻新后的服装简直像新的一样！细节处理得非常到位，完全看不出修补痕迹。"</p>
                            <p class="text-right text-sm font-bold mt-2">— 小林，资深Cosplayer</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 服装租赁区域 -->
    <section id="rent" class="py-16 md:py-24 bg-gray-50">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-16">
                <h2 class="text-[clamp(1.8rem,4vw,2.5rem)] font-bold text-dark mb-4">服装租赁服务</h2>
                <p class="text-lg text-gray-600 max-w-2xl mx-auto">灵活的租赁方案，满足您不同场合的Cosplay需求，无需担心服装存放问题</p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-1 gap-8 mb-12">
                <!-- 租赁方案1 -->
                <div class="bg-white rounded-xl shadow-lg overflow-hidden transition-custom hover:shadow-xl mx-auto max-w-md">
                    <div class="bg-primary/10 p-6 text-center">
                        <h3 class="text-xl font-bold mb-2">日常租赁</h3>
                        <p class="text-gray-600">适合个人日常拍摄或小型活动</p>
                    </div>
                    <div class="p-6">
                        <div class="text-center mb-6">
                            <span class="text-4xl font-bold text-dark">¥120</span>
                            <span class="text-gray-500">/天</span>
                        </div>
                        <ul class="space-y-3 mb-8">
                            <li class="flex items-start">
                                <i class="fa fa-check text-accent mt-1 mr-3"></i>
                                <span>单套服装租赁</span>
                            </li>
                            <li class="flex items-start">
                                <i class="fa fa-check text-accent mt-1 mr-3"></i>
                                <span>基础配饰包含</span>
                            </li>
                            <li class="flex items-start">
                                <i class="fa fa-check text-accent mt-1 mr-3"></i>
                                <span>免费配送与回收</span>
                            </li>
                            <li class="flex items-start">
                                <i class="fa fa-check text-accent mt-1 mr-3"></i>
                                <span>轻微污渍免赔</span>
                            </li>
                        </ul>
                        <a href="#" class="block w-full bg-white border-2 border-primary text-primary hover:bg-primary hover:text-white text-center px-6 py-3 rounded-full font-medium transition-custom">
                            选择方案
                        </a>
                    </div>
                </div>
            </div>

            <div class="bg-white p-8 rounded-xl shadow-md max-w-4xl mx-auto">
                <h4 class="text-xl font-bold mb-4 text-center">租赁流程</h4>
                <div class="flex flex-col md:flex-row justify-between items-center">
                    <div class="flex flex-col items-center mb-6 md:mb-0">
                        <div class="w-12 h-12 bg-primary rounded-full flex items-center justify-center text-white font-bold mb-3">1</div>
                        <p class="text-center font-medium">选择服装与租期</p>
                    </div>
                    <div class="hidden md:block w-1/4 h-1 bg-gray-200 relative">
                        <div class="absolute top-0 left-0 w-full h-full bg-primary"></div>
                    </div>
                    <div class="hidden md:block text-2xl text-primary">→</div>
                    <div class="flex flex-col items-center mb-6 md:mb-0">
                        <div class="w-12 h-12 bg-primary rounded-full flex items-center justify-center text-white font-bold mb-3">2</div>
                        <p class="text-center font-medium">确认订单与配送</p>
                    </div>
                    <div class="hidden md:block w-1/4 h-1 bg-gray-200 relative">
                        <div class="absolute top-0 left-0 w-full h-full bg-primary"></div>
                    </div>
                    <div class="hidden md:block text-2xl text-primary">→</div>
                    <div class="flex flex-col items-center mb-6 md:mb-0">
                        <div class="w-12 h-12 bg-primary rounded-full flex items-center justify-center text-white font-bold mb-3">3</div>
                        <p class="text-center font-medium">使用与维护</p>
                    </div>
                    <div class="hidden md:block w-1/4 h-1 bg-gray-200 relative">
                        <div class="absolute top-0 left-0 w-full h-full bg-primary"></div>
                    </div>
                    <div class="hidden md:block text-2xl text-primary">→</div>
                    <div class="flex flex-col items-center">
                        <div class="w-12 h-12 bg-primary rounded-full flex items-center justify-center text-white font-bold mb-3">4</div>
                        <p class="text-center font-medium">归还与验收</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 专业合作区域 -->
    <section id="collaborate" class="py-16 md:py-24 bg-white">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-16">
                <h2 class="text-[clamp(1.8rem,4vw,2.5rem)] font-bold text-dark mb-4">专业团队合作</h2>
                <p class="text-lg text-gray-600 max-w-2xl mx-auto">与资深化妆师和摄影师合作，为您打造完美的Cosplay造型和专业的拍摄体验</p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 gap-12 mb-16">
                <!-- 化妆师合作 -->
                <div class="bg-gray-50 rounded-xl overflow-hidden shadow-lg transition-custom hover:shadow-xl">
                    <div class="h-60 overflow-hidden">
                        <img src="Desktop/WechatIMG25.jpg" alt="专业化妆师合作" class="w-full h-full object-cover transition-custom hover:scale-110 duration-[700ms]">
                    </div>
                    <div class="p-6">
                        <h3 class="text-2xl font-bold mb-4 text-dark">专业化妆师团队</h3>
                        <p class="text-gray-600 mb-6">
                            我们的合作化妆师均有5年以上Cosplay妆容经验，熟悉各类动漫角色的妆容特点，能够精准还原角色形象。从日常妆容到特效妆容，满足您的各种需求。
                        </p>
                        <div class="grid grid-cols-2 gap-4 mb-6">
                            <div class="bg-white p-3 rounded-lg shadow-sm">
                                <h4 class="font-bold mb-1">日常妆容</h4>
                                <p class="text-sm text-gray-600">¥288起/人</p>
                            </div>
                            <div class="bg-white p-3 rounded-lg shadow-sm">
                                <h4 class="font-bold mb-1">精致妆容</h4>
                                <p class="text-sm text-gray-600">¥488起/人</p>
                            </div>
                            <div class="bg-white p-3 rounded-lg shadow-sm">
                                <h4 class="font-bold mb-1">特效妆容</h4>
                                <p class="text-sm text-gray-600">¥888起/人</p>
                            </div>
                            <div class="bg-white p-3 rounded-lg shadow-sm">
                                <h4 class="font-bold mb-1">团队妆容</h4>
                                <p class="text-sm text-gray-600">¥2000起/团队</p>
                            </div>
                        </div>
                        <a href="#" class="inline-block bg-secondary hover:bg-secondary/90 text-white px-6 py-3 rounded-full font-medium transition-custom shadow-md hover:shadow-lg">
                            查看化妆师列表
                        </a>
                    </div>
                </div>

                <!-- 摄影师合作 -->
                <div class="bg-gray-50 rounded-xl overflow-hidden shadow-lg transition-custom hover:shadow-xl">
                    <div class="h-60 overflow-hidden">
                        <img src="Desktop/WechatIMG22_副本.jpg" alt="专业摄影师合作" class="w-full h-full object-cover transition-custom hover:scale-110 duration-[700ms]">
                    </div>
                    <div class="p-6">
                        <h3 class="text-2xl font-bold mb-4 text-dark">专业摄影师团队</h3>
                        <p class="text-gray-600 mb-6">
                            我们的合作摄影师擅长Cosplay主题拍摄，拥有丰富的外景和棚拍经验。配备专业的摄影设备和后期团队，为您提供高质量的成片和精修服务。
                        </p>
                        <div class="grid grid-cols-2 gap-4 mb-6">
                            <div class="bg-white p-3 rounded-lg shadow-sm">
                                <h4 class="font-bold mb-1">基础拍摄</h4>
                                <p class="text-sm text-gray-600">¥588起/2小时</p>
                            </div>
                            <div class="bg-white p-3 rounded-lg shadow-sm">
                                <h4 class="font-bold mb-1">精致拍摄</h4>
                                <p class="text-sm text-gray-600">¥1288起/4小时</p>
                            </div>
                            <div class="bg-white p-3 rounded-lg shadow-sm">
                                <h4 class="font-bold mb-1">外景拍摄</h4>
                                <p class="text-sm text-gray-600">¥1688起/半天</p>
                            </div>
                            <div class="bg-white p-3 rounded-lg shadow-sm">
                                <h4 class="font-bold mb-1">定制套餐</h4>
                                <p class="text-sm text-gray-600">¥2888起/天</p>
                            </div>
                        </div>
                        <a href="#" class="inline-block bg-primary hover:bg-primary/90 text-white px-6 py-3 rounded-full font-medium transition-custom shadow-md hover:shadow-lg">
                            查看摄影师作品
                        </a>
                    </div>
                </div>
            </div>

            <!-- 合作流程 -->
            <div class="bg-primary/5 rounded-2xl p-8 md:p-12">
                <h3 class="text-2xl font-bold mb-8 text-center text-dark">一站式合作流程</h3>
                <div class="grid grid-cols-1 md:grid-cols-4 gap-8">
                    <div class="text-center">
                        <div class="w-16 h-16 bg-primary rounded-full flex items-center justify-center text-white text-2xl font-bold mx-auto mb-4">1</div>
                        <h4 class="text-lg font-bold mb-2">需求沟通</h4>
                        <p class="text-gray-600">告知我们您的角色需求和活动安排</p>
                    </div>
                    <div class="text-center">
                        <div class="w-16 h-16 bg-primary rounded-full flex items-center justify-center text-white text-2xl font-bold mx-auto mb-4">2</div>
                        <h4 class="text-lg font-bold mb-2">方案定制</h4>
                        <p class="text-gray-600">我们为您定制服装、化妆和拍摄方案</p>
                    </div>
                    <div class="text-center">
                        <div class="w-16 h-16 bg-primary rounded-full flex items-center justify-center text-white text-2xl font-bold mx-auto mb-4">3</div>
                        <h4 class="text-lg font-bold mb-2">服务实施</h4>
                        <p class="text-gray-600">专业团队为您提供一站式服务</p>
                    </div>
                    <div class="text-center">
                        <div class="w-16 h-16 bg-primary rounded-full flex items-center justify-center text-white text-2xl font-bold mx-auto mb-4">4</div>
                        <h4 class="text-lg font-bold mb-2">成果交付</h4>
                        <p class="text-gray-600">按时交付服装、妆容和摄影作品</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 预约区域 -->
    <section id="booking" class="py-16 md:py-24 bg-gradient-to-br from-primary/10 to-secondary/10">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="max-w-4xl mx-auto bg-white rounded-2xl shadow-xl overflow-hidden">
                <div class="flex flex-col md:flex-row">
                    <div class="md:w-1/2 bg-primary p-8 md:p-12 flex flex-col justify-center">
                        <h2 class="text-3xl font-bold text-white mb-6">立即预约服务</h2>
                        <p class="text-white/90 mb-8">
                            填写下方表单预约我们的服务，我们的客服人员将在24小时内与您联系，为您提供详细的咨询和方案定制。
                        </p>
                        <div class="space-y-6">
                            <div class="flex items-start">
                                <div class="bg-white/20 p-3 rounded-full mr-4">
                                    <i class="fa fa-phone text-white"></i>
                                </div>
                                <div>
                                    <h4 class="text-white font-bold mb-1">电话咨询</h4>
                                    <p class="text-white/80">400-123-4567</p>
                                </div>
                            </div>
                            <div class="flex items-start">
                                <div class="bg-white/20 p-3 rounded-full mr-4">
                                    <i class="fa fa-weixin text-white"></i>
                                </div>
                                <div>
                                    <h4 class="text-white font-bold mb-1">微信咨询</h4>
                                    <p class="text-white/80">Coserbox-Service</p>
                                </div>
                            </div>
                            <div class="flex items-start">
                                <div class="bg-white/20 p-3 rounded-full mr-4">
                                    <i class="fa fa-envelope text-white"></i>
                                </div>
                                <div>
                                    <h4 class="text-white font-bold mb-1">邮件咨询</h4>
                                    <p class="text-white/80">service@coserbox.com</p>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="md:w-1/2 p-8 md:p-12">
                        <form id="booking-form" class="space-y-6">
                            <div>
                                <label for="name" class="block text-gray-700 font-medium mb-2">您的姓名</label>
                                <input type="text" id="name" name="name" class="w-full px-4 py-3 rounded-full border-2 border-neonPink/50 focus:border-neonPink bg-light/80 placeholder-gray-400 focus:ring-2 focus:ring-neonPink/30 transition-custom">
                            </div>
                            <div>
                                <label for="phone" class="block text-gray-700 font-medium mb-2">联系电话</label>
                                <input type="tel" id="phone" name="phone" class="w-full px-4 py-3 rounded-full border-2 border-neonBlue/50 focus:border-neonBlue bg-light/80 placeholder-gray-400 focus:ring-2 focus:ring-neonBlue/30 transition-custom">
                            </div>
                            <div>
                                <label for="service" class="block text-gray-700 font-medium mb-2">预约服务类型</label>
                                <select id="service" name="service" class="w-full px-4 py-3 rounded-full border-2 border-neonGreen/50 focus:border-neonGreen bg-light/80 placeholder-gray-400 focus:ring-2 focus:ring-neonGreen/30 transition-custom appearance-none bg-[url('data:image/svg+xml;charset=UTF-8,%3csvg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="%23FF6AD5" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"%3e%3cpolyline points="6 9 12 15 18 9"%3e%3c/polyline%3e%3c/svg%3e')] bg-no-repeat bg-right-[10px] bg-center pr-10">
                                    <option value="">请选择服务类型</option>
                                    <option value="buy">二手服装购买</option>
                                    <option value="renovation">服装翻新服务</option>
                                    <option value="rent">服装租赁服务</option>
                                    <option value="makeup">化妆服务</option>
                                    <option value="photography">摄影服务</option>
                                    <option value="package">一站式套餐服务</option>
                                </select>
                            </div>
                            <div>
                                <label for="date" class="block text-gray-700 font-medium mb-2">预计使用日期</label>
                                <input type="date" id="date" name="date" class="w-full px-4 py-3 rounded-full border-2 border-neonPink/50 focus:border-neonPink bg-light/80 placeholder-gray-400 focus:ring-2 focus:ring-neonPink/30 transition-custom">
                            </div>
                            <div>
                                <label for="message" class="block text-gray-700 font-medium mb-2">需求描述</label>
                                <textarea id="message" name="message" rows="4" class="w-full px-4 py-3 rounded-2xl border-2 border-neonBlue/50 focus:border-neonBlue bg-light/80 placeholder-gray-400 focus:ring-2 focus:ring-neonBlue/30 transition-custom resize-none">
                            </div>
                            <button type="submit" class="w-full bg-gradient-to-r from-neonPink to-neonBlue hover:from-neonPink/90 hover:to-neonBlue/90 text-white font-bold py-3 px-6 rounded-full transition-custom shadow-lg hover:shadow-neonPink/50 transform hover:scale-105">
                                提交预约
                            </button>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 客户评价 -->
    <section class="py-16 md:py-24 bg-white">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-16">
                <h2 class="text-[clamp(1.8rem,4vw,2.5rem)] font-bold text-dark mb-4">客户评价</h2>
                <p class="text-lg text-gray-600 max-w-2xl mx-auto">听听我们的客户怎么说，他们的满意是我们最大的动力</p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <!-- 评价1 -->
                <div class="bg-gray-50 p-6 rounded-xl shadow-md transition-custom hover:shadow-lg">
                    <div class="text-yellow-400 flex mb-4">
                        <i class="fa fa-star"></i>
                        <i class="fa fa-star"></i>
                        <i class="fa fa-star"></i>
                        <i class="fa fa-star"></i>
                        <i class="fa fa-star"></i>
                    </div>
                    <p class="text-gray-600 mb-6 italic">
                        "第一次尝试Cosplay，选择了Coserbox的一站式服务。从服装租赁到化妆再到摄影，全程都很专业，最终的成片效果非常满意！"
                    </p>
                    <div class="flex items-center">
                        <img src="Desktop/WechatIMG193.jpg" alt="客户头像" class="w-12 h-12 rounded-full object-cover mr-4">
                        <div>
                            <h4 class="font-bold">小明</h4>
                            <p class="text-sm text-gray-500">初次Cosplayer</p>
                        </div>
                    </div>
                </div>

                <!-- 评价2 -->
                <div class="bg-gray-50 p-6 rounded-xl shadow-md transition-custom hover:shadow-lg">
                    <div class="text-yellow-400 flex mb-4">
                        <i class="fa fa-star"></i>
                        <i class="fa fa-star"></i>
                        <i class="fa fa-star"></i>
                        <i class="fa fa-star"></i>
                        <i class="fa fa-star"></i>
                    </div>
                    <p class="text-gray-600 mb-6 italic">
                        "作为一名资深Cosplayer，我经常需要各种服装和配饰。Coserbox的二手服装质量很好，翻新服务也很专业，帮我节省了很多成本。"
                    </p>
                    <div class="flex items-center">
                        <img src="Desktop/WechatIMG196.jpg" alt="客户头像" class="w-12 h-12 rounded-full object-cover mr-4">
                        <div>
                            <h4 class="font-bold">阿杰</h4>
                            <p class="text-sm text-gray-500">资深Cosplayer</p>
                        </div>
                    </div>
                </div>

                <!-- 评价3 -->
                <div class="bg-gray-50 p-6 rounded-xl shadow-md transition-custom hover:shadow-lg">
                    <div class="text-yellow-400 flex mb-4">
                        <i class="fa fa-star"></i>
                        <i class="fa fa-star"></i>
                        <i class="fa fa-star"></i>
                        <i class="fa fa-star"></i>
                        <i class="fa fa-star-half-o"></i>
                    </div>
                    <p class="text-gray-600 mb-6 italic">
                        "公司年会需要Cosplay表演，通过Coserbox租了10套服装，还预约了化妆团队。整个过程非常顺利，同事们都很满意，下次活动还会选择他们！"
                    </p>
                    <div class="flex items-center">
                        <img src="Desktop/WechatIMG197.jpg" alt="客户头像" class="w-12 h-12 rounded-full object-cover mr-4">
                        <div>
                            <h4 class="font-bold">李经理</h4>
                            <p class="text-sm text-gray-500">企业客户</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 联系我们 -->
    <section id="contact" class="py-16 md:py-24 bg-gray-50">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex flex-col md:flex-row gap-12">
                <div class="md:w-1/2">
                    <h2 class="text-[clamp(1.8rem,4vw,2.5rem)] font-bold text-dark mb-6">联系我们</h2>
                    <p class="text-lg text-gray-600 mb-8">
                        如果您有任何问题或需求，欢迎通过以下方式联系我们。我们的客服团队将竭诚为您提供帮助和支持。
                    </p>

                    <div class="space-y-6 mb-8">
                        <div class="flex items-start">
                            <div class="bg-primary/10 p-3 rounded-full mr-4">
                                <i class="fa fa-map-marker text-primary"></i>
                            </div>
                            <div>
                                <h4 class="font-bold mb-1">实体店地址</h4>
                                <p class="text-gray-600">上海市静安区南京西路1266号恒隆广场46楼</p>
                            </div>
                        </div>
                        <div class="flex items-start">
                            <div class="bg-primary/10 p-3 rounded-full mr-4">
                                <i class="fa fa-clock-o text-primary"></i>
                            </div>
                            <div>
                                <h4 class="font-bold mb-1">营业时间</h4>
                                <p class="text-gray-600">周一至周五: 10:00 - 20:00</p>
                                <p class="text-gray-600">周六至周日: 10:00 - 22:00</p>
                            </div>
                        </div>
                        <div class="flex items-start">
                            <div class="bg-primary/10 p-3 rounded-full mr-4">
                                <i class="fa fa-phone text-primary"></i>
                            </div>
                            <div>
                                <h4 class="font-bold mb-1">联系电话</h4>
                                <p class="text-gray-600">400-123-4567</p>
                            </div>
                        </div>
                        <div class="flex items-start">
                            <div class="bg-primary/10 p-3 rounded-full mr-4">
                                <i class="fa fa-envelope text-primary"></i>
                            </div>
                            <div>
                                <h4 class="font-bold mb-1">电子邮箱</h4>
                                <p class="text-gray-600">info@coserbox.com</p>
                            </div>
                        </div>
                    </div>

                    <div class="flex space-x-4">
                        <a href="#" class="bg-primary/10 hover:bg-primary/20 text-primary p-3 rounded-full transition-custom">
                            <i class="fa fa-weibo"></i>
                        </a>
                        <a href="#" class="bg-primary/10 hover:bg-primary/20 text-primary p-3 rounded-full transition-custom">
                            <i class="fa fa-weixin"></i>
                        </a>
                        <a href="#" class="bg-primary/10 hover:bg-primary/20 text-primary p-3 rounded-full transition-custom">
                            <i class="fa fa-instagram"></i>
                        </a>
                        <a href="#" class="bg-primary/10 hover:bg-primary/20 text-primary p-3 rounded-full transition-custom">
                            <i class="fa fa-bilibili"></i>
                        </a>
                    </div>
                </div>
                <div class="md:w-1/2">
                    <div class="bg-white p-8 rounded-xl shadow-lg">
                        <h3 class="text-2xl font-bold mb-6">发送消息</h3>
                        <form class="space-y-6">
                            <div class="grid grid-cols-1 sm:grid-cols-2 gap-6">
                                <div>
                                    <label for="contact-name" class="block text-gray-700 font-medium mb-2">您的姓名</label>
                                    <input type="text" id="contact-name" name="contact-name" class="w-full px-4 py-3 rounded-lg border border-gray-300 focus:outline-none focus:ring-2 focus:ring-primary focus:border-transparent transition-custom" placeholder="请输入您的姓名">
                                </div>
                                <div>
                                    <label for="contact-email" class="block text-gray-700 font-medium mb-2">电子邮箱</label>
                                    <input type="email" id="contact-email" name="contact-email" class="w-full px-4 py-3 rounded-lg border border-gray-300 focus:outline-none focus:ring-2 focus:ring-primary focus:border-transparent transition-custom" placeholder="请输入您的电子邮箱">
                                </div>
                            </div>
                            <div>
                                <label for="contact-subject" class="block text-gray-700 font-medium mb-2">主题</label>
                                <input type="text" id="contact-subject" name="contact-subject" class="w-full px-4 py-3 rounded-lg border border-gray-300 focus:outline-none focus:ring-2 focus:ring-primary focus:border-transparent transition-custom" placeholder="请输入消息主题">
                            </div>
                            <div>
                                <label for="contact-message" class="block text-gray-700 font-medium mb-2">消息内容</label>
                                <textarea id="contact-message" name="contact-message" rows="5" class="w-full px-4 py-3 rounded-lg border border-gray-300 focus:outline-none focus:ring-2 focus:ring-primary focus:border-transparent transition-custom" placeholder="请输入您的消息内容"></textarea>
                            </div>
                            <button type="submit" class="w-full bg-primary hover:bg-primary/90 text-white font-medium py-3 px-6 rounded-lg transition-custom shadow-md hover:shadow-lg">
                                发送消息
                            </button>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 页脚 -->
    <footer class="bg-dark text-white py-12 md:py-16">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-12 mb-12">
                <div>
                    <h3 class="text-2xl font-bold mb-6">Coserbox</h3>
                    <p class="text-gray-400 mb-6">
                        一站式Cosplay服务平台，为您提供服装购买、翻新、租赁以及专业化妆和摄影服务。
                    </p>
                    <div class="flex space-x-4">
                        <a href="#" class="text-gray-400 hover:text-white transition-custom">
                            <i class="fa fa-weibo"></i>
                        </a>
                        <a href="#" class="text-gray-400 hover:text-white transition-custom">
                            <i class="fa fa-weixin"></i>
                        </a>
                        <a href="#" class="text-gray-400 hover:text-white transition-custom">
                            <i class="fa fa-instagram"></i>
                        </a>
                        <a href="#" class="text-gray-400 hover:text-white transition-custom">
                            <i class="fa fa-bilibili"></i>
                        </a>
                    </div>
                </div>
                <div>
                    <h4 class="text-lg font-bold mb-6">服务项目</h4>
                    <ul class="space-y-4">
                        <li><a href="#buy" class="text-gray-400 hover:text-white transition-custom">二手服装购买</a></li>
                        <li><a href="#renovation" class="text-gray-400 hover:text-white transition-custom">服装翻新服务</a></li>
                        <li><a href="#rent" class="text-gray-400 hover:text-white transition-custom">服装租赁服务</a></li>
                        <li><a href="#collaborate" class="text-gray-400 hover:text-white transition-custom">化妆服务</a></li>
                        <li><a href="#collaborate" class="text-gray-400 hover:text-white transition-custom">摄影服务</a></li>
                        <li><a href="#booking" class="text-gray-400 hover:text-white transition-custom">一站式套餐</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="text-lg font-bold mb-6">关于我们</h4>
                    <ul class="space-y-4">
                        <li><a href="#" class="text-gray-400 hover:text-white transition-custom">公司简介</a></li>
                        <li><a href="#" class="text-gray-400 hover:text-white transition-custom">服务流程</a></li>
                        <li><a href="#" class="text-gray-400 hover:text-white transition-custom">价格说明</a></li>
                        <li><a href="#" class="text-gray-400 hover:text-white transition-custom">常见问题</a></li>
                        <li><a href="#" class="text-gray-400 hover:text-white transition-custom">招贤纳士</a></li>
                        <li><a href="#contact" class="text-gray-400 hover:text-white transition-custom">联系我们</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="text-lg font-bold mb-6">联系方式</h4>
                    <ul class="space-y-4">
                        <li class="flex items-start">
                            <i class="fa fa-map-marker mt-1 mr-3 text-gray-400"></i>
                            <span class="text-gray-400">上海市静安区南京西路1266号恒隆广场46楼</span>
                        </li>
                        <li class="flex items-start">
                            <i class="fa fa-phone mt-1 mr-3 text-gray-400"></i>
                            <span class="text-gray-400">400-123-4567</span>
                        </li>
                        <li class="flex items-start">
                            <i class="fa fa-envelope mt-1 mr-3 text-gray-400"></i>
                            <span class="text-gray-400">info@coserbox.com</span>
                        </li>
                        <li class="flex items-start">
                            <i class="fa fa-clock-o mt-1 mr-3 text-gray-400"></i>
                            <span class="text-gray-400">10:00 - 20:00 (周一至周日)</span>
                        </li>
                    </ul>
                </div>
            </div>
            <div class="border-t border-gray-800 pt-8">
                <div class="flex flex-col md:flex-row justify-between items-center">
                    <p class="text-gray-400 mb-4 md:mb-0">© 2023 Coserbox. All rights reserved.</p>
                    <div class="flex space-x-6">}
                        <a href="#" class="text-gray-400 hover:text-white transition-custom">隐私政策</a>
                        <a href="#" class="text-gray-400 hover:text-white transition-custom">服务条款</a>
                        <a href="#" class="text-gray-400 hover:text-white transition-custom">Cookie政策</a>
                    </div>
                </div>
            </div>
        </div>
    </footer>

    <!-- JavaScript -->
    <script>
        // 导航栏滚动效果
        window.addEventListener('scroll', function() {
            const navbar = document.getElementById('navbar');
            if (window.scrollY > 50) {
                navbar.classList.add('shadow-md');
                navbar.classList.remove('bg-white/90');
                navbar.classList.add('bg-white');
            } else {
                navbar.classList.remove('shadow-md');
                navbar.classList.add('bg-white/90');
                navbar.classList.remove('bg-white');
            }
        });

        // 移动端菜单切换
        document.getElementById('menu-toggle').addEventListener('click', function() {
            const mobileMenu = document.getElementById('mobile-menu');
            mobileMenu.classList.toggle('hidden');
        });

        // 平滑滚动
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const targetId = this.getAttribute('href');
                if (targetId === '#') return;
                const targetElement = document.querySelector(targetId);
                if (targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 80,
                        behavior: 'smooth'
                    });
                    // 关闭移动菜单
                    document.getElementById('mobile-menu').classList.add('hidden');
                }
            });
        });

        // 表单提交处理
        document.getElementById('booking-form').addEventListener('submit', function(e) {
            e.preventDefault();
            // 这里添加表单验证和提交逻辑
            alert('预约表单提交成功！我们的客服将尽快与您联系。');
            this.reset();
        });

        // 图片懒加载
        document.addEventListener("DOMContentLoaded", function() {
            const lazyImages = document.querySelectorAll("img");
            if ('IntersectionObserver' in window) {
                const imageObserver = new IntersectionObserver(function(entries, observer) {
                    entries.forEach(function(entry) {
                        if (entry.isIntersecting) {
                            const image = entry.target;
                            image.classList.add('fade-in');
                            imageObserver.unobserve(image);
                        }
                    });
                });
                lazyImages.forEach(function(image) {
                    imageObserver.observe(image);
                });
            }
        });
    </script>
</body>
</html>
