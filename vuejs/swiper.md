# Sử dụng Swiper với Vuejs
## Cài đặt swiper vào dự án
`-> npm i swiper`
## Sử dụng 2 componet quan trọng là `Swiper` và `Swiper-Slide`
```
<template>
  <swiper
    :slides-per-view="3"
    :space-between="50"
    @swiper="onSwiper"
    @slideChange="onSlideChange"
  >
    <swiper-slide>Slide 1</swiper-slide>
    <swiper-slide>Slide 2</swiper-slide>
    <swiper-slide>Slide 3</swiper-slide>
  </swiper>
</template>
<script>
  // Import Swiper Vue.js components
  import { Swiper, SwiperSlide } from 'swiper/vue';

  // Import Swiper styles
  import 'swiper/css';

  export default {
    components: {
      Swiper,
      SwiperSlide,
    },
    setup() {
      const onSwiper = (swiper) => {
        console.log(swiper);
      };
      const onSlideChange = () => {
        console.log('slide change');
      };
      return {
        onSwiper,
        onSlideChange,
      };
    },
  };
</script>
```
## Một số modules phổ biến hay sử dụng của `swiper`
* `Navigation` -> Hai nút bấm tiến là lùi
* `Pagination` -> Chấm tròn hiển thị số lượng của slider
* `Autoplay` -> Khi slider trượt đến slide cuối thì cho phép chạy ngược lại slide đầu tiên
* `EffectFade` ->  Hiệu ứng mờ khi chuyển slide
* `EffectCube` -> Hiệu ứng khối khi chuyển slide
* `EffectFlip` ->  Hiệu ứng lật khi chuyển slide
* `EffectCarts` -> Hiệu ứng thẻ khi chuyển slide
* `EffectCoverflow` -> Hiệu ứng dòng chảy khi chuyển slide
## Các style tương ứng cần import vào dự án khi sử dụng của các module trên 
* `Navigation` -> swiper/css/navigation
* `Pagination` -> swiper/css/pagination
* `Autoplay` -> swiper/css/autoplay
* `EffectFade` ->  swiper/css/effect-fade
* `EffectCube` -> swiper/css/effect-cube
* `EffectFlip` ->  swiper/css/effect-flip
* `EffectCarts` -> swiper/css/effect-cards
* `EffectCoverflow` -> swiper/css/effect-coverflow
## Các `props` hay sử dụng trong `swiper`
* `:slides-per-view="value"` với `value` là số lượng slide sẽ hiển thị trên slider
* `:space-between="value"` với `value` là khoảng cách giữa các slide
* `:slides-per-group="value"` với `value` là số lượng slide sẽ chuyển khi người dùng chuyển slide
* ` :speed="value"` với `value` là tốc độ khi chuyển slide
* `:loop="boolean" ` với `boolean` là true hoặc false -> khi người dùng chuyển đến slide cuối mặc định sẽ không next tiếp được thay đổi thành true để làm được việc đó
* `effect="value"` với `value` là hiệu ứng của slide(overflow, fade, cube, flip,...)
* ` :pagination="{ clickable: true }"` -> pagination là các chấm tròn theo dõi tiến độ slide nhận một object có key là `clickable` -> Khi người dùng click vào các chấm tròn bên dưới slider thì slide sẽ chuyển sang vị trí tương ứng
* `:autoplay="{delay: 2000, disableOnInteraction: false, pauseOnMouseEnter: true,}"`
    * `Autoplay` -> cho phép các slide tự chuyển trong một khoảng thời gian nhất định 
    * `delay: 2000` -> sau 2s slider sẽ chuển một cách tự động quá slide khác
    * `disableOnInteraction: false`-> Khi người dùng tương tác với slider thì autoplay sẽ vẫn khởi chạy sau mỗi lần tương tác, để thay đổi hãy sửa lại thành true(default value)
    * `pauseOnMouseEnter: true` -> Khi người dùng di chuyển con trỏ chuột vào thành phần slide thì thuộc tính autoplay sẽ không được kích hoạt, mục đích để tránh trường hợp khi người dùng đang xem sản phẩm trên slide mà bị next đi slide khác
* `:breakpoints="{ width: {key: value} }` -> Responsive slider 
    * `width` -> Là chiều ngang màn hình 
    * `key: value` -> Các thuộc tính cần thay đổi
    * `Ví dụ` -> {920: {slidesPerView: 4, spaceBetween: 15}} -> Slider sẽ hiển thị 4 slide và khoảng cách giữa chúng là 15px khi màn hình có width>=920
