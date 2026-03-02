<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CBRE 文件上传与展示平台</title>
    <!-- 引入Tailwind CSS简化样式开发 -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- 引入Font Awesome图标库 -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    <!-- 自定义Tailwind配置 -->
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        cbre: {
                            green: '#00664F', // CBRE品牌绿
                            dark: '#003328',
                            light: '#E8F4F1'
                        },
                        neutral: {
                            100: '#F5F5F5',
                            200: '#E5E5E5',
                            800: '#262626'
                        }
                    },
                    fontFamily: {
                        sans: ['Inter', 'system-ui', 'sans-serif']
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
            .transition-height {
                transition: max-height 0.3s ease-in-out;
            }
            .file-drop-active {
                @apply border-cbre-green bg-cbre-light/50;
            }
        }
    </style>
</head>
<body class="font-sans text-neutral-800 bg-white min-h-screen flex flex-col">
    <!-- 头部导航 -->
    <header class="bg-white shadow-sm sticky top-0 z-50">
        <div class="container mx-auto px-4 py-4 flex items-center justify-between">
            <!-- CBRE Logo -->
            <div class="flex items-center">
                <div class="text-cbre-green text-3xl font-bold">CBRE</div>
                <span class="ml-2 text-sm text-neutral-800 hidden md:inline-block">世邦魏理仕文件管理平台</span>
            </div>
            <!-- 导航菜单 -->
            <nav class="hidden md:flex items-center space-x-8">
                <a href="#about" class="text-neutral-800 hover:text-cbre-green transition-colors">关于我们</a>
                <a href="#upload" class="text-neutral-800 hover:text-cbre-green transition-colors">报价文件上传</a>
                <a href="#gallery" class="text-neutral-800 hover:text-cbre-green transition-colors">项目展示</a>
                <a href="#contact" class="text-neutral-800 hover:text-cbre-green transition-colors">联系方式</a>
            </nav>
            <!-- 移动端菜单按钮 -->
            <button id="menuBtn" class="md:hidden text-neutral-800 focus:outline-none">
                <i class="fa-solid fa-bars text-xl"></i>
            </button>
        </div>
        <!-- 移动端菜单 -->
        <div id="mobileMenu" class="md:hidden max-h-0 overflow-hidden transition-height bg-white border-t border-neutral-200">
            <div class="container mx-auto px-4 py-2 flex flex-col space-y-4">
                <a href="#about" class="py-2 text-neutral-800 hover:text-cbre-green transition-colors">关于我们</a>
                <a href="#upload" class="py-2 text-neutral-800 hover:text-cbre-green transition-colors">报价文件上传</a>
                <a href="#gallery" class="py-2 text-neutral-800 hover:text-cbre-green transition-colors">项目展示</a>
                <a href="#contact" class="py-2 text-neutral-800 hover:text-cbre-green transition-colors">联系方式</a>
            </div>
        </div>
    </header>

    <!-- 主内容区 -->
    <main class="flex-grow">
        <!-- 英雄区 -->
        <section class="bg-cbre-green/5 py-16 md:py-24">
            <div class="container mx-auto px-4 text-center">
                <h1 class="text-[clamp(2rem,5vw,3.5rem)] font-bold text-cbre-dark mb-6">CBRE 世邦魏理仕</h1>
                <p class="text-[clamp(1rem,2vw,1.25rem)] text-neutral-800 max-w-3xl mx-auto mb-8">
                    全球领先的商业地产服务和投资公司，提供专业的地产解决方案与报价文件管理服务
                </p>
                <a href="#upload" class="inline-block bg-cbre-green text-white px-8 py-3 rounded-md hover:bg-cbre-dark transition-colors shadow-md hover:shadow-lg">
                    上传报价文件 <i class="fa-solid fa-upload ml-2"></i>
                </a>
            </div>
        </section>

        <!-- 关于我们 -->
        <section id="about" class="py-16">
            <div class="container mx-auto px-4">
                <h2 class="text-3xl font-bold mb-8 text-center">关于 CBRE</h2>
                <div class="max-w-4xl mx-auto grid md:grid-cols-2 gap-8 items-center">
                    <div>
                        <p class="mb-4 text-lg">
                            CBRE（世邦魏理仕）是全球领先的商业地产服务和投资公司，拥有超过100年的行业经验，业务遍及全球100多个国家和地区。
                        </p>
                        <p class="mb-4 text-lg">
                            我们为客户提供全方位的商业地产解决方案，包括物业管理、租赁代理、估值咨询、投资交易、项目管理等，助力客户实现资产价值最大化。
                        </p>
                        <ul class="mt-6 space-y-2">
                            <li class="flex items-start">
                                <i class="fa-solid fa-check-circle text-cbre-green mt-1 mr-2"></i>
                                <span>全球超过10万名专业员工</span>
                            </li>
                            <li class="flex items-start">
                                <i class="fa-solid fa-check-circle text-cbre-green mt-1 mr-2"></i>
                                <span>覆盖全球主要商业地产市场</span>
                            </li>
                            <li class="flex items-start">
                                <i class="fa-solid fa-check-circle text-cbre-green mt-1 mr-2"></i>
                                <span>专业的地产咨询与解决方案</span>
                            </li>
                        </ul>
                    </div>
                    <div class="bg-neutral-100 rounded-lg p-4">
                        <img src="https://picsum.photos/800/600?random=1" alt="CBRE办公环境" class="w-full h-auto rounded-md shadow-md">
                    </div>
                </div>
            </div>
        </section>

        <!-- 文件上传区域 -->
        <section id="upload" class="py-16 bg-neutral-100">
            <div class="container mx-auto px-4">
                <h2 class="text-3xl font-bold mb-2 text-center">报价文件上传</h2>
                <p class="text-center text-neutral-800 mb-12 max-w-2xl mx-auto">
                    请上传相关报价文件，支持多种格式，上传后我们将尽快处理并与您联系
                </p>

                <div class="max-w-3xl mx-auto bg-white rounded-lg shadow-md p-6 md:p-8">
                    <form id="uploadForm" class="space-y-6">
                        <!-- 基本信息 -->
                        <div class="grid md:grid-cols-2 gap-6">
                            <div>
                                <label for="name" class="block text-sm font-medium text-neutral-800 mb-1">联系人姓名 *</label>
                                <input type="text" id="name" name="name" required
                                    class="w-full px-4 py-2 border border-neutral-200 rounded-md focus:outline-none focus:ring-2 focus:ring-cbre-green focus:border-transparent">
                            </div>
                            <div>
                                <label for="phone" class="block text-sm font-medium text-neutral-800 mb-1">联系电话 *</label>
                                <input type="tel" id="phone" name="phone" required
                                    class="w-full px-4 py-2 border border-neutral-200 rounded-md focus:outline-none focus:ring-2 focus:ring-cbre-green focus:border-transparent">
                            </div>
                            <div class="md:col-span-2">
                                <label for="email" class="block text-sm font-medium text-neutral-800 mb-1">电子邮箱</label>
                                <input type="email" id="email" name="email"
                                    class="w-full px-4 py-2 border border-neutral-200 rounded-md focus:outline-none focus:ring-2 focus:ring-cbre-green focus:border-transparent">
                            </div>
                            <div class="md:col-span-2">
                                <label for="project" class="block text-sm font-medium text-neutral-800 mb-1">项目名称 *</label>
                                <input type="text" id="project" name="project" required
                                    class="w-full px-4 py-2 border border-neutral-200 rounded-md focus:outline-none focus:ring-2 focus:ring-cbre-green focus:border-transparent">
                            </div>
                        </div>

                        <!-- 文件上传 -->
                        <div class="md:col-span-2">
                            <label class="block text-sm font-medium text-neutral-800 mb-2">报价文件上传 *</label>
                            <!-- 拖拽上传区域 -->
                            <div id="fileDropArea" class="border-2 border-dashed border-neutral-200 rounded-md p-8 text-center hover:border-cbre-green transition-colors">
                                <i class="fa-solid fa-cloud-upload text-4xl text-cbre-green mb-4"></i>
                                <p class="mb-2">拖拽文件至此处上传，或</p>
                                <label class="inline-block bg-cbre-green text-white px-6 py-2 rounded-md cursor-pointer hover:bg-cbre-dark transition-colors">
                                    选择文件
                                    <input type="file" id="fileInput" name="file" multiple accept=".pdf,.doc,.docx,.xls,.xlsx,.jpg,.png" class="hidden">
                                </label>
                                <p class="mt-4 text-sm text-neutral-800/70">支持格式：PDF、Word、Excel、图片 (最大单文件20MB)</p>
                            </div>
                            <!-- 已选文件列表 -->
                            <div id="fileList" class="mt-4 space-y-2 hidden"></div>
                        </div>

                        <!-- 备注信息 -->
                        <div class="md:col-span-2">
                            <label for="remark" class="block text-sm font-medium text-neutral-800 mb-1">备注信息</label>
                            <textarea id="remark" name="remark" rows="4"
                                class="w-full px-4 py-2 border border-neutral-200 rounded-md focus:outline-none focus:ring-2 focus:ring-cbre-green focus:border-transparent"></textarea>
                        </div>

                        <!-- 提交按钮 -->
                        <div class="md:col-span-2 text-center">
                            <button type="submit" class="bg-cbre-green text-white px-8 py-3 rounded-md hover:bg-cbre-dark transition-colors shadow-md hover:shadow-lg w-full md:w-auto">
                                提交文件 <i class="fa-solid fa-paper-plane ml-2"></i>
                            </button>
                        </div>
                    </form>
                </div>
            </div>
        </section>

        <!-- 图片展示区 -->
        <section id="gallery" class="py-16">
            <div class="container mx-auto px-4">
                <h2 class="text-3xl font-bold mb-2 text-center">项目展示</h2>
                <p class="text-center text-neutral-800 mb-12 max-w-2xl mx-auto">
                    展示CBRE参与的经典商业地产项目，见证专业服务成果
                </p>

                <!-- 图片网格 -->
                <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6 max-w-6xl mx-auto">
                    <!-- 图片项1 -->
                    <div class="group relative overflow-hidden rounded-lg shadow-md">
                        <img src="https://picsum.photos/800/600?random=2" alt="商业综合体项目" 
                            class="w-full h-64 object-cover transition-transform duration-500 group-hover:scale-110">
                        <div class="absolute inset-0 bg-cbre-dark/70 opacity-0 group-hover:opacity-100 transition-opacity flex items-center justify-center">
                            <p class="text-white text-lg font-medium px-4 text-center">商业综合体项目</p>
                        </div>
                    </div>
                    <!-- 图片项2 -->
                    <div class="group relative overflow-hidden rounded-lg shadow-md">
                        <img src="https://picsum.photos/800/600?random=3" alt="写字楼租赁项目" 
                            class="w-full h-64 object-cover transition-transform duration-500 group-hover:scale-110">
                        <div class="absolute inset-0 bg-cbre-dark/70 opacity-0 group-hover:opacity-100 transition-opacity flex items-center justify-center">
                            <p class="text-white text-lg font-medium px-4 text-center">写字楼租赁项目</p>
                        </div>
                    </div>
                    <!-- 图片项3 -->
                    <div class="group relative overflow-hidden rounded-lg shadow-md">
                        <img src="https://picsum.photos/800/600?random=4" alt="产业园区规划" 
                            class="w-full h-64 object-cover transition-transform duration-500 group-hover:scale-110">
                        <div class="absolute inset-0 bg-cbre-dark/70 opacity-0 group-hover:opacity-100 transition-opacity flex items-center justify-center">
                            <p class="text-white text-lg font-medium px-4 text-center">产业园区规划</p>
                        </div>
                    </div>
                    <!-- 图片项4 -->
                    <div class="group relative overflow-hidden rounded-lg shadow-md">
                        <img src="https://picsum.photos/800/600?random=5" alt="酒店资产管理" 
                            class="w-full h-64 object-cover transition-transform duration-500 group-hover:scale-110">
                        <div class="absolute inset-0 bg-cbre-dark/70 opacity-0 group-hover:opacity-100 transition-opacity flex items-center justify-center">
                            <p class="text-white text-lg font-medium px-4 text-center">酒店资产管理</p>
                        </div>
                    </div>
                    <!-- 图片项5 -->
                    <div class="group relative overflow-hidden rounded-lg shadow-md">
                        <img src="https://picsum.photos/800/600?random=6" alt="零售商业顾问" 
                            class="w-full h-64 object-cover transition-transform duration-500 group-hover:scale-110">
                        <div class="absolute inset-0 bg-cbre-dark/70 opacity-0 group-hover:opacity-100 transition-opacity flex items-center justify-center">
                            <p class="text-white text-lg font-medium px-4 text-center">零售商业顾问</p>
                        </div>
                    </div>
                    <!-- 图片项6 -->
                    <div class="group relative overflow-hidden rounded-lg shadow-md">
                        <img src="https://picsum.photos/800/600?random=7" alt="物流仓储解决方案" 
                            class="w-full h-64 object-cover transition-transform duration-500 group-hover:scale-110">
                        <div class="absolute inset-0 bg-cbre-dark/70 opacity-0 group-hover:opacity-100 transition-opacity flex items-center justify-center">
                            <p class="text-white text-lg font-medium px-4 text-center">物流仓储解决方案</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- 联系方式 -->
        <section id="contact" class="py-16 bg-cbre-light/30">
            <div class="container mx-auto px-4">
                <h2 class="text-3xl font-bold mb-2 text-center">联系方式</h2>
                <p class="text-center text-neutral-800 mb-12 max-w-2xl mx-auto">
                    如有任何问题或需求，欢迎随时联系我们，CBRE专业团队将为您提供优质服务
                </p>

                <div class="max-w-4xl mx-auto grid md:grid-cols-2 gap-8">
                    <!-- 联系信息 -->
                    <div class="bg-white rounded-lg shadow-md p-6 md:p-8">
                        <h3 class="text-xl font-bold mb-6 text-cbre-green">联系我们</h3>
                        <ul class="space-y-4">
                            <li class="flex items-start">
                                <i class="fa-solid fa-map-marker-alt text-cbre-green text-xl mt-1 mr-4"></i>
                                <div>
                                    <p class="font-medium">公司地址</p>
                                    <p class="text-neutral-800/80">上海市浦东新区世纪大道1号环球金融中心</p>
                                </div>
                            </li>
                            <li class="flex items-start">
                                <i class="fa-solid fa-phone text-cbre-green text-xl mt-1 mr-4"></i>
                                <div>
                                    <p class="font-medium">联系电话</p>
                                    <p class="text-neutral-800/80">400-888-8888</p>
                                </div>
                            </li>
                            <li class="flex items-start">
                                <i class="fa-solid fa-envelope text-cbre-green text-xl mt-1 mr-4"></i>
                                <div>
                                    <p class="font-medium">电子邮箱</p>
                                    <p class="text-neutral-800/80">contact@cbre.com.cn</p>
                                </div>
                            </li>
                            <li class="flex items-start">
                                <i class="fa-solid fa-clock text-cbre-green text-xl mt-1 mr-4"></i>
                                <div>
                                    <p class="font-medium">工作时间</p>
                                    <p class="text-neutral-800/80">周一至周五 9:00 - 18:00</p>
                                </div>
                            </li>
                        </ul>
                        <!-- 社交媒体 -->
                        <div class="mt-8">
                            <p class="font-medium mb-4">关注我们</p>
                            <div class="flex space-x-4">
                                <a href="#" class="w-10 h-10 rounded-full bg-cbre-green text-white flex items-center justify-center hover:bg-cbre-dark transition-colors">
                                    <i class="fa-brands fa-weixin"></i>
                                </a>
                                <a href="#" class="w-10 h-10 rounded-full bg-cbre-green text-white flex items-center justify-center hover:bg-cbre-dark transition-colors">
                                    <i class="fa-brands fa-weibo"></i>
                                </a>
                                <a href="#" class="w-10 h-10 rounded-full bg-cbre-green text-white flex items-center justify-center hover:bg-cbre-dark transition-colors">
                                    <i class="fa-brands fa-linkedin"></i>
                                </a>
                            </div>
                        </div>
                    </div>

                    <!-- 简易留言框 -->
                    <div class="bg-white rounded-lg shadow-md p-6 md:p-8">
                        <h3 class="text-xl font-bold mb-6 text-cbre-green">发送留言</h3>
                        <form id="contactForm" class="space-y-4">
                            <div>
                                <label for="contactName" class="block text-sm font-medium text-neutral-800 mb-1">您的姓名 *</label>
                                <input type="text" id="contactName" name="contactName" required
                                    class="w-full px-4 py-2 border border-neutral-200 rounded-md focus:outline-none focus:ring-2 focus:ring-cbre-green focus:border-transparent">
                            </div>
                            <div>
                                <label for="contactPhone" class="block text-sm font-medium text-neutral-800 mb-1">联系电话 *</label>
                                <input type="tel" id="contactPhone" name="contactPhone" required
                                    class="w-full px-4 py-2 border border-neutral-200 rounded-md focus:outline-none focus:ring-2 focus:ring-cbre-green focus:border-transparent">
                            </div>
                            <div>
                                <label for="contactMessage" class="block text-sm font-medium text-neutral-800 mb-1">留言内容 *</label>
                                <textarea id="contactMessage" name="contactMessage" rows="4" required
                                    class="w-full px-4 py-2 border border-neutral-200 rounded-md focus:outline-none focus:ring-2 focus:ring-cbre-green focus:border-transparent"></textarea>
                            </div>
                            <button type="submit" class="w-full bg-cbre-green text-white px-6 py-3 rounded-md hover:bg-cbre-dark transition-colors shadow-md hover:shadow-lg">
                                发送留言 <i class="fa-solid fa-paper-plane ml-2"></i>
                            </button>
                        </form>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- 页脚 -->
    <footer class="bg-cbre-dark text-white py-12">
        <div class="container mx-auto px-4">
            <div class="grid md:grid-cols-4 gap-8">
                <div>
                    <h4 class="text-xl font-bold mb-4">CBRE</h4>
                    <p class="text-white/70 mb-4">全球领先的商业地产服务和投资公司</p>
                    <p class="text-white/70">© 2025 CBRE Group, Inc. 保留所有权利</p>
                </div>
                <div>
                    <h4 class="text-lg font-bold mb-4">服务项目</h4>
                    <ul class="space-y-2 text-white/70">
                        <li><a href="#" class="hover:text-white transition-colors">物业管理</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">租赁代理</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">估值咨询</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">投资交易</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="text-lg font-bold mb-4">关于我们</h4>
                    <ul class="space-y-2 text-white/70">
                        <li><a href="#" class="hover:text-white transition-colors">公司简介</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">全球网络</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">新闻中心</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">招贤纳士</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="text-lg font-bold mb-4">法律信息</h4>
                    <ul class="space-y-2 text-white/70">
                        <li><a href="#" class="hover:text-white transition-colors">隐私政策</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">使用条款</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">Cookie政策</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">法律声明</a></li>
                    </ul>
                </div>
            </div>
            <div class="mt-8 pt-8 border-t border-white/20 text-center text-white/50 text-sm">
                本网站仅为展示用途，如有实际业务需求请联系CBRE官方渠道
            </div>
        </div>
    </footer>

    <!-- 成功提示弹窗 -->
    <div id="successModal" class="fixed inset-0 bg-black/50 flex items-center justify-center z-50 hidden">
        <div class="bg-white rounded-lg shadow-xl p-8 max-w-md w-full">
            <div class="text-center">
                <i class="fa-solid fa-check-circle text-4xl text-green-500 mb-4"></i>
                <h3 class="text-xl font-bold mb-2">提交成功</h3>
                <p class="mb-6 text-neutral-800/80">您的文件已成功提交，我们将尽快与您联系</p>
                <button id="closeModal" class="bg-cbre-green text-white px-6 py-2 rounded-md hover:bg-cbre-dark transition-colors">
                    确定
                </button>
            </div>
        </div>
    </div>

    <!-- JavaScript -->
    <script>
        // 移动端菜单切换
        const menuBtn = document.getElementById('menuBtn');
        const mobileMenu = document.getElementById('mobileMenu');
        menuBtn.addEventListener('click', () => {
            if (mobileMenu.style.maxHeight === '0px' || !mobileMenu.style.maxHeight) {
                mobileMenu.style.maxHeight = mobileMenu.scrollHeight + 'px';
                menuBtn.innerHTML = '<i class="fa-solid fa-xmark text-xl"></i>';
            } else {
                mobileMenu.style.maxHeight = '0px';
                menuBtn.innerHTML = '<i class="fa-solid fa-bars text-xl"></i>';
            }
        });

        // 平滑滚动
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const targetId = this.getAttribute('href');
                const targetElement = document.querySelector(targetId);
                if (targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 80,
                        behavior: 'smooth'
                    });
                    // 关闭移动端菜单
                    if (mobileMenu.style.maxHeight !== '0px') {
                        mobileMenu.style.maxHeight = '0px';
                        menuBtn.innerHTML = '<i class="fa-solid fa-bars text-xl"></i>';
                    }
                }
            });
        });

        // 文件上传功能
        const fileDropArea = document.getElementById('fileDropArea');
        const fileInput = document.getElementById('fileInput');
        const fileList = document.getElementById('fileList');

        // 阻止默认拖拽行为
        ['dragenter', 'dragover', 'dragleave', 'drop'].forEach(eventName => {
            fileDropArea.addEventListener(eventName, preventDefaults, false);
            document.body.addEventListener(eventName, preventDefaults, false);
        });

        function preventDefaults(e) {
            e.preventDefault();
            e.stopPropagation();
        }

        // 高亮拖拽区域
        ['dragenter', 'dragover'].forEach(eventName => {
            fileDropArea.addEventListener(eventName, highlight, false);
        });

        ['dragleave', 'drop'].forEach(eventName => {
            fileDropArea.addEventListener(eventName, unhighlight, false);
        });

        function highlight() {
            fileDropArea.classList.add('file-drop-active');
        }

        function unhighlight() {
            fileDropArea.classList.remove('file-drop-active');
        }

        // 处理文件放下
        fileDropArea.addEventListener('drop', handleDrop, false);
        function handleDrop(e) {
            const dt = e.dataTransfer;
            const files = dt.files;
            handleFiles(files);
        }

        // 处理文件选择
        fileInput.addEventListener('change', function() {
            handleFiles(this.files);
        });

        // 处理文件列表
        function handleFiles(files) {
            if (files.length === 0) return;
            
            fileList.classList.remove('hidden');
            fileList.innerHTML = '';
            
            Array.from(files).forEach((file, index) => {
                // 验证文件大小
                if (file.size > 20 * 1024 * 1024) {
                    const fileItem = document.createElement('div');
                    fileItem.className = 'flex items-center justify-between p-2 bg-red-50 border border-red-200 rounded-md';
                    fileItem.innerHTML = `
                        <div class="flex items-center">
                            <i class="fa-solid fa-file-excel text-red-500 mr-2"></i>
                            <span>${file.name}</span>
                        </div>
                        <span class="text-red-500 text-sm">文件过大（超过20MB）</span>
                    `;
                    fileList.appendChild(fileItem);
                    return;
                }

                const fileItem = document.createElement('div');
                fileItem.className = 'flex items-center justify-between p-2 bg-neutral-100 border border-neutral-200 rounded-md';
                
                // 根据文件类型显示不同图标
                let fileIcon = 'fa-file';
                if (file.type.includes('pdf')) fileIcon = 'fa-file-pdf';
                else if (file.type.includes('word')) fileIcon = 'fa-file-word';
                else if (file.type.includes('excel')) fileIcon = 'fa-file-excel';
                else if (file.type.includes('image')) fileIcon = 'fa-file-image';
                
                fileItem.innerHTML = `
                    <div class="flex items-center">
                        <i class="fa-solid ${fileIcon} text-cbre-green mr-2"></i>
                        <span>${file.name}</span>
                    </div>
                    <button class="text-neutral-800/70 hover:text-red-500" onclick="removeFile(this, ${index})">
                        <i class="fa-solid fa-times"></i>
                    </button>
                `;
                fileList.appendChild(fileItem);
            });
        }

        // 移除文件
        window.removeFile = function(btn, index) {
            const fileItem = btn.closest('div');
            fileItem.remove();
            
            // 如果列表为空，隐藏列表
            if (fileList.children.length === 0) {
                fileList.classList.add('hidden');
            }
            
            // 重置fileInput（简单处理，实际项目需更完善）
            fileInput.value = '';
        };

        // 表单提交
        const uploadForm = document.getElementById('uploadForm');
        const contactForm = document.getElementById('contactForm');
        const successModal = document.getElementById('successModal');
        const closeModal = document.getElementById('closeModal');

        uploadForm.addEventListener('submit', function(e) {
            e.preventDefault();
            // 模拟提交
            setTimeout(() => {
                successModal.classList.remove('hidden');
                uploadForm.reset();
                fileList.classList.add('hidden');
                fileList.innerHTML = '';
            }, 1000);
        });

        contactForm.addEventListener('submit', function(e) {
            e.preventDefault();
            // 模拟提交
            setTimeout(() => {
                successModal.classList.remove('hidden');
                contactForm.reset();
            }, 1000);
        });

        closeModal.addEventListener('click', function() {
            successModal.classList.add('hidden');
        });

        // 点击模态框外部关闭
        successModal.addEventListener('click', function(e) {
            if (e.target === successModal) {
                successModal.classList.add('hidden');
            }
        });

        // 监听滚动，添加导航栏阴影
        window.addEventListener('scroll', function() {
            const header = document.querySelector('header');
            if (window.scrollY > 10) {
                header.classList.add('shadow');
            } else {
                header.classList.remove('shadow');
            }
        });
    </script>
</body>
</html>
