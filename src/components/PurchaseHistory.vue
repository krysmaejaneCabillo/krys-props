<script>
export default {
    props: {
        checkoutItem: {
            type: Array,

        },

    },
    data() {
        return {

        };
    },

    methods: {

    }
}
</script>

<template>

    <body class="bg-pink-50 text-[#222222] antialiased">

        <div class="max-w-[1200px] mx-auto px-4 pt-4 text-xs text-gray-500 flex items-center space-x-1">
            <a href="#" class="hover:underline">Home</a>
            <span>/</span>
            <span class="text-gray-900">Personal Center</span>
        </div>

        <main class="max-w-[1200px] mx-auto px-4 py-6 flex flex-col md:flex-row gap-8">

            <aside class="w-full md:w-[240px] flex-shrink-0">
                <h2 class="text-sm font-bold text-gray-900 uppercase tracking-wider mb-4 border-b border-gray-100 pb-2">
                    Personal Center</h2>

                <div class="mb-5">
                    <div
                        class="flex items-center justify-between text-xs font-bold text-gray-800 mb-2 cursor-pointer group">
                        <span>My Account</span>
                        <i class="fa-solid fa-minus text-[10px] text-gray-400"></i>
                    </div>
                    <ul class="space-y-2.5 pl-1 text-xs text-gray-600">
                        <li><a href="#" class="hover:text-[#ff4b7d] flex items-center">
                                <svg class="h-4 w-4" width="16" height="16" viewBox="0 0 16 16" fill="none"
                                    xmlns="http://www.w3.org/2000/svg">
                                    <path fill-rule="evenodd" clip-rule="evenodd"
                                        d="M10.7863 9.64834C10.7863 9.91625 10.7232 10.171 10.5971 10.4125C10.4709 10.654 10.2946 10.8669 10.0682 11.0511C9.84145 11.2362 9.57318 11.3838 9.26271 11.4939C8.95206 11.6039 8.60914 11.6592 8.23395 11.6592C7.89748 11.6592 7.59521 11.6414 7.32659 11.6055C7.05815 11.5698 6.80576 11.5134 6.56959 11.4359C6.33359 11.3581 6.10702 11.2583 5.89038 11.1364C5.67357 11.0143 5.44874 10.8669 5.21588 10.6938L6.28319 9.7017C6.59401 9.94035 6.89786 10.1085 7.1956 10.207C7.49317 10.3054 7.81673 10.3543 8.16592 10.3543C8.30826 10.3543 8.44256 10.335 8.56867 10.2963C8.69513 10.2575 8.80502 10.2054 8.89868 10.1399C8.99235 10.0742 9.06683 9.99675 9.12195 9.90733C9.17671 9.81808 9.20427 9.71973 9.20427 9.61228C9.20427 9.49929 9.1816 9.39827 9.1366 9.30884C9.09107 9.21942 9.01049 9.13267 8.8938 9.04914C8.77746 8.96578 8.61559 8.88118 8.40855 8.79479C8.20151 8.7084 7.93621 8.61147 7.61282 8.50438C7.32816 8.40889 7.05484 8.30001 6.79285 8.17774C6.53087 8.05601 6.30115 7.90839 6.10388 7.73561C5.90643 7.56283 5.74788 7.36025 5.62822 7.12767C5.50839 6.89527 5.44874 6.62147 5.44874 6.30536C5.44874 6.00174 5.51502 5.72187 5.64776 5.4652C5.78014 5.20906 5.96137 4.99041 6.19126 4.80852C6.42081 4.62664 6.68925 4.48528 6.99676 4.38389C7.30374 4.28269 7.63567 4.23199 7.99133 4.23199C8.58664 4.23199 9.08811 4.30339 9.49556 4.44636C9.90337 4.58951 10.2655 4.79817 10.5824 5.0718L9.53446 6.04619C9.34015 5.87359 9.12334 5.74097 8.8842 5.64851C8.64472 5.55623 8.36337 5.51 8.03981 5.51C7.89103 5.51 7.75358 5.53088 7.62748 5.57265C7.50119 5.61424 7.3927 5.66957 7.30235 5.73775C7.21165 5.80665 7.13874 5.88679 7.08397 5.97925C7.02903 6.07171 7.00147 6.16845 7.00147 6.26984C7.00147 6.38318 7.02711 6.48563 7.07926 6.57809C7.13071 6.67037 7.2181 6.7598 7.34124 6.84619C7.46404 6.93276 7.62748 7.01915 7.8312 7.10536C8.03511 7.19175 8.28872 7.28564 8.59309 7.38702C8.98118 7.51214 9.31434 7.64905 9.59272 7.79826C9.87075 7.94713 10.0972 8.11081 10.2718 8.28965C10.4465 8.4685 10.5759 8.66966 10.6602 8.89278C10.7441 9.11643 10.7863 9.3681 10.7863 9.64834Z"
                                        fill="currentColor"></path>
                                    <path fill-rule="evenodd" clip-rule="evenodd"
                                        d="M11.8419 1.34546L15.6523 7.98169L11.8104 14.6361L4.15805 14.6544L0.347656 8.01814L4.18961 1.36368L11.8419 1.34546ZM5.11464 2.96148L2.19391 8.02033L5.08308 13.0522L10.8854 13.0383L13.8061 7.97949L10.9169 2.94767L5.11464 2.96148Z"
                                        fill="currentColor"></path>
                                </svg>
                                KRYS CLUB <span
                                    class="ml-1 bg-[#ffeaef] text-[#ff4b7d] scale-90 px-1 rounded-sm text-[9px] font-semibold">KRYS
                                    CLUB</span></a></li>
                        <li><a href="#" class="hover:text-[#ff4b7d] flex items-center"><svg
                                    style="width:18px;height:18px;" width="24" height="24" viewBox="0 0 24 24"
                                    fill="none" xmlns="http://www.w3.org/2000/svg">
                                    <path fill-rule="evenodd" clip-rule="evenodd"
                                        d="M5.852 1C8.49669 1 9.45661 3.1278 9.59122 4.30093C9.63678 4.70475 9.34788 5.06715 8.94507 5.11374C8.91607 5.11788 8.88811 5.11892 8.86015 5.11892C8.49358 5.11892 8.17672 4.84556 8.13219 4.47281C8.10527 4.25848 7.80497 2.46927 5.84371 2.46927C5.76709 2.46927 5.68839 2.47134 5.60658 2.47755C5.59105 2.47859 5.57552 2.47859 5.55999 2.47859C5.17374 2.47859 4.85066 2.18245 4.82477 1.79313C4.79785 1.38828 5.10332 1.03831 5.50821 1.01139C5.62522 1.00414 5.74016 1 5.852 1Z"
                                        fill="currentColor"></path>
                                    <path fill-rule="evenodd" clip-rule="evenodd"
                                        d="M15.3486 14.8312C15.2668 14.7494 15.1694 14.6841 15.0597 14.6375C14.951 14.5909 14.8308 14.5682 14.7045 14.5682H11.5659C11.0937 14.5682 10.6432 14.476 10.228 14.2958C9.81483 14.1157 9.44826 13.8672 9.13864 13.5566C8.82799 13.2459 8.57946 12.8784 8.39928 12.4621C8.21807 12.0448 8.12695 11.5934 8.12695 11.1212C8.12695 10.6491 8.21911 10.1987 8.39928 9.78343C8.57946 9.3703 8.82799 9.00376 9.13864 8.69313C9.44929 8.3825 9.81587 8.134 10.228 7.95384C10.6432 7.77264 11.0937 7.68152 11.5659 7.68152H17.1732L16.4203 5.61274C16.2681 5.19547 15.9616 4.85378 15.564 4.65705L10.1441 1.97944C9.92459 1.87072 9.69989 2.11094 9.81897 2.32424C10.2218 3.04282 10.5262 3.91983 10.5687 4.49759C10.635 5.41912 9.82001 6.17084 8.8953 6.17084C7.97059 6.17084 7.25091 5.44501 7.22709 4.54315C7.18878 4.29879 7.03966 3.75726 6.49084 3.50669C6.38522 3.45906 6.25992 3.50669 6.21333 3.61231L3.88964 8.90643C3.71153 9.31231 3.69601 9.77203 3.84823 10.1894L6.10253 16.3812H14.7035C14.8308 16.3812 14.9499 16.3574 15.0586 16.3118C15.1684 16.2652 15.2658 16.2 15.3476 16.1182C15.4294 16.0364 15.4946 15.9391 15.5402 15.8293C15.5868 15.7206 15.6095 15.6005 15.6095 15.4742C15.6095 15.3478 15.5857 15.2277 15.5402 15.119C15.4936 15.0093 15.4283 14.9119 15.3465 14.8301L15.3486 14.8312Z"
                                        fill="currentColor"></path>
                                    <path fill-rule="evenodd" clip-rule="evenodd"
                                        d="M20.6865 17.333L18.0967 10.2166H11.5667C11.4394 10.2166 11.3203 10.2404 11.2116 10.2859C11.1018 10.3325 11.0045 10.3978 10.9227 10.4796C10.8409 10.5614 10.7756 10.6587 10.729 10.7684C10.6835 10.8772 10.6596 10.9962 10.6596 11.1236C10.6596 11.2509 10.6835 11.3721 10.729 11.4839C10.7756 11.5957 10.8398 11.6931 10.9216 11.7749C11.0034 11.8567 11.1008 11.9219 11.2105 11.9685C11.3193 12.0141 11.4383 12.0379 11.5657 12.0379H14.7043C15.1765 12.0379 15.627 12.1279 16.0443 12.306C16.4606 12.4841 16.8292 12.7316 17.1388 13.0412C17.4495 13.3518 17.697 13.7194 17.874 14.1356C18.0521 14.5529 18.1422 15.0044 18.1422 15.4755C18.1422 15.9466 18.0521 16.397 17.874 16.8122C17.6959 17.2264 17.4484 17.5929 17.1388 17.9025C16.8282 18.2131 16.4606 18.4616 16.0443 18.6418C15.627 18.823 15.1755 18.9141 14.7033 18.9141H7.02393L8.11329 21.9065C8.42705 22.769 9.38074 23.2132 10.2434 22.8995L19.6924 19.4608C20.5539 19.1471 20.9992 18.1945 20.6854 17.332L20.6865 17.333Z"
                                        fill="currentColor"></path>
                                </svg> KRYS Saver <span
                                    class="ml-1 bg-amber-100 text-amber-700 scale-90 px-1 rounded-sm text-[9px]">SAVE
                                    MORE</span></a></li>
                        <li><a href="#" class="hover:text-[#ff4b7d] flex items-center"><svg
                                    style="width:18px;height:18px;" width="24" height="24" viewBox="0 0 24 24"
                                    fill="none" xmlns="http://www.w3.org/2000/svg">
                                    <path
                                        d="M20.7263 8.73097H20.3796L20.2581 8.43927C20.233 8.37914 20.217 8.3042 20.217 8.23399C20.217 7.95683 20.4491 7.72475 20.7263 7.72475C21.0275 7.72475 21.2514 7.95785 21.26 8.22845C21.2562 8.50264 21.0257 8.73097 20.7508 8.73097H20.7263ZM19.8598 9.4069L19.9945 9.35073L18.0782 17.5981H5.8728L3.96045 9.36772L4.08624 9.42395L7.78495 11.0773L8.36568 11.3369L8.70952 10.8018L11.8571 5.90282L11.9514 5.756L12.0281 5.88753L14.8817 10.7865L15.2078 11.3464L15.8059 11.097L19.8598 9.4069ZM3.71634 8.43828L3.57839 8.73717L3.23794 8.73109C2.96214 8.72617 2.73999 8.49842 2.73999 8.22174C2.73999 7.95404 2.96254 7.72475 3.24922 7.72475C3.52639 7.72475 3.75846 7.95682 3.75846 8.23399C3.75846 8.31584 3.74282 8.38091 3.71634 8.43828ZM12.257 4.89935L11.9544 5.10112L11.6558 4.89439C11.5353 4.81098 11.4479 4.65781 11.4479 4.48628C11.4479 4.20912 11.68 3.97705 11.9571 3.97705C12.2343 3.97705 12.4664 4.20912 12.4664 4.48628C12.4664 4.67167 12.3784 4.81842 12.257 4.89935Z"
                                        stroke="currentColor" stroke-width="1.48"></path>
                                </svg> KRYS VIP</a></li>
                        <li><a href="#" class="hover:text-[#ff4b7d] flex items-center"><svg
                                    style="width:18px;height:18px;" width="24" height="24" viewBox="0 0 24 24"
                                    fill="none" xmlns="http://www.w3.org/2000/svg">
                                    <path fill-rule="evenodd" clip-rule="evenodd"
                                        d="M12.0001 2.5C14.7615 2.5 17.0001 4.73858 17.0001 7.5C17.0001 10.1888 14.8777 12.3818 12.2169 12.4954L12.0001 12.5C9.23863 12.5 7.00006 10.2614 7.00006 7.5C7.00006 4.81125 9.12236 2.61818 11.7832 2.50462L12.0001 2.5ZM21.5022 21.4996C20.7234 16.957 16.766 13.5 12.0011 13.5L11.7218 13.504C7.08233 13.636 3.26361 17.046 2.50012 21.4996H21.5022ZM5.38579 19.3125C6.71588 17.0185 9.19999 15.5 12.0011 15.5L12.2549 15.5042C14.9518 15.5927 17.3267 17.088 18.6165 19.3125L18.7211 19.499H5.28106L5.38579 19.3125ZM9.00006 7.5C9.00006 5.84315 10.3432 4.5 12.0001 4.5C13.6569 4.5 15.0001 5.84315 15.0001 7.5C15.0001 9.15685 13.6569 10.5 12.0001 10.5C10.3432 10.5 9.00006 9.15685 9.00006 7.5Z"
                                        fill="currentColor"></path>
                                </svg> My Profile <span
                                    class="ml-1 bg-red-500 text-white text-[9px] px-1 rounded-sm font-bold">+POINTS</span></a>
                        </li>
                        <li><a href="#" class="hover:text-[#ff4b7d] flex items-center"><svg
                                    style="width:18px;height:18px;" width="24" height="24" viewBox="0 0 24 24"
                                    fill="none" xmlns="http://www.w3.org/2000/svg">
                                    <path fill-rule="evenodd" clip-rule="evenodd"
                                        d="M12 5.91675C9.7448 5.91675 7.91663 7.74492 7.91663 10.0001C7.91663 12.2553 9.7448 14.0834 12 14.0834C14.2552 14.0834 16.0833 12.2553 16.0833 10.0001C16.0833 7.74492 14.2552 5.91675 12 5.91675ZM12 7.41675C13.4267 7.41675 14.5833 8.57334 14.5833 10.0001C14.5833 11.4268 13.4267 12.5834 12 12.5834C10.5733 12.5834 9.41663 11.4268 9.41663 10.0001C9.41663 8.57334 10.5733 7.41675 12 7.41675Z"
                                        fill="currentColor"></path>
                                    <path fill-rule="evenodd" clip-rule="evenodd"
                                        d="M12 1.25C7.16835 1.25 3.25 5.14873 3.25 9.95996C3.25 13.2414 4.82842 16.5507 7.86783 19.7639C8.84936 20.8015 9.94443 21.7846 11.1151 22.6824L11.5559 23.0135L12 23.3398L12.4441 23.0135C12.5893 22.9068 12.7365 22.7963 12.885 22.6824C14.0556 21.7846 15.1507 20.8015 16.1322 19.7639C19.1716 16.5507 20.75 13.2414 20.75 9.95996C20.75 5.14873 16.8317 1.25 12 1.25ZM12 2.75C16.0049 2.75 19.25 5.97885 19.25 9.95996C19.25 12.8173 17.838 15.7777 15.0425 18.7331L14.4739 19.3144C13.8928 19.8893 13.2748 20.4443 12.6281 20.9728L12 21.4695L12.0279 21.4922C10.9195 20.6421 9.88368 19.7122 8.95755 18.7331C6.16205 15.7777 4.75 12.8173 4.75 9.95996C4.75 5.97884 7.99509 2.75 12 2.75Z"
                                        fill="currentColor"></path>
                                </svg> Address Book</a></li>
                        <li><a href="#" class="hover:text-[#ff4b7d] flex items-center"><svg
                                    style="width:18px;height:18px;" width="32" height="32" viewBox="0 0 32 32"
                                    fill="none" xmlns="http://www.w3.org/2000/svg">
                                    <path fill-rule="evenodd" clip-rule="evenodd"
                                        d="M29 27V5H3V27H29ZM5 25V13.3333H27V25H5ZM25 19V21H18.6667V19H25ZM27 11.3333H5V7H27V11.3333Z"
                                        fill="currentColor"></path>
                                </svg>My Payment Options</a>
                        </li>
                        <li><a href="#" class="hover:text-[#ff4b7d] flex items-center"><svg
                                    style="width:18px;height:18px;" width="24" height="24" viewBox="0 0 24 24"
                                    fill="none" xmlns="http://www.w3.org/2000/svg">
                                    <path
                                        d="M8.48433 2.92009L2.92004 8.48438L15.5572 21.1216L21.1215 15.5573L8.48433 2.92009Z"
                                        stroke="currentColor" stroke-width="1.3"></path>
                                    <path d="M5.66711 10.9718L7.43534 9.20361" stroke="currentColor" stroke-width="1.3">
                                    </path>
                                    <path d="M8.02478 13.3293L10.9718 10.3823" stroke="currentColor" stroke-width="1.3">
                                    </path>
                                    <path d="M10.3824 15.6871L12.1507 13.9189" stroke="currentColor" stroke-width="1.3">
                                    </path>
                                    <path d="M12.7401 18.0449L14.5083 16.2766" stroke="currentColor" stroke-width="1.3">
                                    </path>
                                </svg> My Measurements</a>
                        </li>
                        <li><a href="#" class="hover:text-[#ff4b7d] flex items-center"><svg
                                    style="width:18px;height:18px;" width="24" height="24" viewBox="0 0 24 24"
                                    fill="none" xmlns="http://www.w3.org/2000/svg">
                                    <path fill-rule="evenodd" clip-rule="evenodd"
                                        d="M20 8.5V2.75H3.5V21.25H9V19.75H5V4.25H18.5V8.5H20Z" fill="currentColor">
                                    </path>
                                    <path fill-rule="evenodd" clip-rule="evenodd" d="M11.5 7.75V9.25H7V7.75H11.5Z"
                                        fill="currentColor"></path>
                                    <path fill-rule="evenodd" clip-rule="evenodd" d="M11.5 11.25V12.75H7V11.25H11.5Z"
                                        fill="currentColor"></path>
                                    <path fill-rule="evenodd" clip-rule="evenodd"
                                        d="M16 16.25C17.3807 16.25 18.5 15.1307 18.5 13.75C18.5 12.3693 17.3807 11.25 16 11.25C14.6193 11.25 13.5 12.3693 13.5 13.75C13.5 15.1307 14.6193 16.25 16 16.25ZM16 14.75C16.5523 14.75 17 14.3023 17 13.75C17 13.1977 16.5523 12.75 16 12.75C15.4477 12.75 15 13.1977 15 13.75C15 14.3023 15.4477 14.75 16 14.75Z"
                                        fill="currentColor"></path>
                                    <path fill-rule="evenodd" clip-rule="evenodd"
                                        d="M12.0309 21.25C12.277 19.2768 13.9602 17.75 16 17.75C18.0398 17.75 19.723 19.2768 19.9691 21.25H18.4503C18.2193 20.1094 17.209 19.25 16 19.25C14.791 19.25 13.7807 20.1094 13.5497 21.25H12.0309Z"
                                        fill="currentColor"></path>
                                </svg> Manage My Account <span
                                    class="ml-1 bg-red-500 text-white text-[9px] px-1 rounded-sm font-bold">+POINTS</span></a>
                        </li>
                    </ul>
                </div>

                <div class="mb-5 border-t border-gray-100 pt-3">
                    <div class="flex items-center justify-between text-xs font-bold text-gray-800 mb-2">
                        <span>My Assets</span>
                        <i class="fa-solid fa-plus text-[10px] text-gray-400"></i>
                    </div>
                </div>
                <div class="mb-5 border-t border-gray-100 pt-3">
                    <div class="flex items-center justify-between text-xs font-bold text-gray-800 mb-2">
                        <span>My Orders</span>
                        <i class="fa-solid fa-minus text-[10px] text-gray-400"></i>
                    </div>
                    <ul class="space-y-2.5 pl-1 text-xs text-gray-600">
                        <li><a href="#" class="text-[#ff4b7d] font-bold flex items-center"><i
                                    class="fa-solid fa-list-ul mr-2"></i> All Orders</a></li>
                        <li><a href="#" class="hover:text-[#ff4b7d] flex items-center"><i
                                    class="fa-regular fa-credit-card mr-2 text-gray-400"></i> Unpaid Orders</a></li>
                        <li><a href="#" class="hover:text-[#ff4b7d] flex items-center"><i
                                    class="fa-solid fa-gears mr-2 text-gray-400"></i> Processing Orders</a></li>
                        <li><a href="#" class="hover:text-[#ff4b7d] flex items-center"><i
                                    class="fa-solid fa-truck mr-2 text-gray-400"></i> Shipped Orders</a></li>
                        <li><a href="#" class="hover:text-[#ff4b7d] flex items-center"><i
                                    class="fa-regular fa-comment mr-2 text-gray-400"></i> Review Orders</a></li>
                        <li><a href="#" class="hover:text-[#ff4b7d] flex items-center"><i
                                    class="fa-solid fa-arrow-rotate-left mr-2 text-gray-400"></i> Return Orders</a></li>
                    </ul>
                </div>

                <div class="border-t border-gray-100 pt-3">
                    <div class="flex items-center justify-between text-xs font-bold text-gray-800 mb-2">
                        <span>My Favorites</span>
                        <i class="fa-solid fa-plus text-[10px] text-gray-400"></i>
                    </div>
                </div>
            </aside>

            <section class="flex-1 bg-pink-50">
                <div class="flex items-center justify-between border-b border-gray-200 pb-3 mb-4">
                    <h1 class="text-xl font-bold uppercase tracking-wider text-black">My Orders</h1>

                    <a href="#"
                        class="text-lg text-gray-800 font-bold hover:text-[#ff4b7d] flex items-center px-3 py-1.5 rounded">
                        <img class="animate-pulse duration-300 h-10 w-10"
                            src="//sc.ltwebstatic.com/she_dist/images/orders/sui_icon_package_m-98b46908fa.png"
                            alt="My Package Icon" data-v-ae7cf3de="">
                        <span>Package &gt;</span>
                    </a>
                </div>

                <div
                    class="flex flex-col sm:flex-row sm:items-center justify-between gap-3 border-b border-gray-100 pb-2 mb-12">
                    <div
                        class="flex items-center space-x-6 text-xs text-gray-500 font-medium overflow-x-auto whitespace-nowrap pb-2 sm:pb-0">
                        <a href="#" class="text-[#ff4b7d] font-bold border-b-2 border-[#ff4b7d] pb-2">All orders</a>
                        <a href="#" class="hover:text-[#ff4b7d] pb-2">Unpaid</a>
                        <a href="#" class="hover:text-[#ff4b7d] pb-2">Processing</a>
                        <a href="#" class="hover:text-[#ff4b7d] pb-2">Shipped</a>
                        <a href="#" class="hover:text-[#ff4b7d] pb-2">Review</a>
                        <span class="text-gray-300">|</span>
                        <a href="#" class="hover:text-[#ff4b7d] pb-2 text-gray-400 flex items-center"><i
                                class="fa-regular fa-trash-can mr-1"></i> Deleted Orders History</a>
                    </div>

                    <div class="text-right self-end sm:self-auto">
                        <button class="text-gray-400 hover:text-[#ff4b7d] px-2 py-1">
                            <i class="fa-solid fa-magnifying-glass text-sm"></i>
                        </button>
                    </div>
                </div>

                <div v-if="checkoutItem.length === 0"
                    class="py-20 flex flex-col items-center justify-center text-center">

                    <div
                        class="w-20 h-20 bg-pink-50 rounded-full flex items-center justify-center mb-4 border border-dashed border-gray-200">
                        <svg class="w-10 h-10 text-gray-300" fill="none" stroke="currentColor" stroke-width="1"
                            viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                            <path stroke-linecap="round" stroke-linejoin="round"
                                d="M9 12h6m-6 4h6m2 5H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z">
                            </path>
                        </svg>
                    </div>
                    <p class="text-xs text-gray-400 font-medium tracking-wide">It is empty here ~</p>
                </div>

                <div v-else>
                    <div class="bg-white rounded-3xl shadow-sm p-4 sm:p-5 mb-4 hover:shadow-md transition-all duration-300 border border-pink-100/50"
                        v-for="(items, index) in checkoutItem" :key="items.id">
                        <div class="flex flex-wrap sm:flex-nowrap items-center gap-4">
                            <img :src="items.image" alt="thumbnail"
                                class="w-20 h-20 sm:w-24 sm:h-24 object-cover rounded-2xl shadow-sm hover:scale-105 transition-transform">
                            <div class="flex-1 min-w-[150px]">
                                <h3 class="font-semibold text-gray-800 text-lg mb-1">{{ items.name }}</h3>

                            </div>
                            <div class="font-bold text-gray-800 text-lg w-full sm:w-auto text-right sm:text-left">
                                ${{ (items.price) }}
                            </div>
                            <button
                                class="text-rose-400 hover:text-rose-600 w-8 h-8 flex items-center justify-center rounded-full hover:bg-rose-50 transition-colors text-xl font-bold ml-auto sm:ml-0">
                                ×
                            </button>
                        </div>
                    </div>
                </div>


                <div class="mt-12 max-w-md border border-gray-200 p-5 rounded-none bg-pink-50">
                    <h4 class="text-xs font-bold text-gray-800 mb-3">Can't find your order?</h4>
                    <div
                        class="flex items-center justify-between border border-gray-300 px-3 py-2 text-xs text-gray-500 cursor-pointer hover:border-black transition-colors rounded-sm">
                        <span>Self-service to find order</span>
                        <svg class="text-[10px] text-gray-400" aria-hidden="true"
                            xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" viewBox="0 0 24 24">
                            <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                d="m10 16 4-4-4-4" />
                        </svg>

                    </div>
                </div>

            </section>
        </main>

        <div class="fixed right-4 bottom-24 flex flex-col space-y-2 z-40">
            <button class="w-20 h-20 flex items-center justify-center">
                <img class="base-img__inner lazyload base-img__cover"
                    src="//img.ltwebstatic.com/v4/p/ccc/2026/05/22/d1/1779433934b9fbca642d38c630180df29f1232435f_thumbnail_220x.webp"
                    data-src="https://img.ltwebstatic.com/v4/p/ccc/2026/05/22/d1/1779433934b9fbca642d38c630180df29f1232435f.png"
                    data-design-width="124" data-exp="" alt="seasonal promotional activities​" loaded="true"
                    style="object-position: initial;">
            </button>
            <button class="w-20 h-20 flex items-center justify-center text-gray-600 hover:text-[#ff4b7d]">
                <img src="//sc.ltwebstatic.com/she_dist/images/shein-right-config-coupon-82b37f3015.gif" alt=""
                    style="width: 30px; height: 22.5px;">
            </button>
        </div>


    </body>

</template>