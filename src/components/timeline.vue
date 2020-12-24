<template>
  <div class="timeline-container">
    <div class="timeline-block timeline-block-right">
      <div class="marker"></div>
      <div class="timeline-content">
        <h3>Phase 1</h3>
        <p>{{$t('section4.item1')}}</p>
      </div>
    </div>

    <div class="timeline-block timeline-block-left">
      <div class="marker"></div>
      <div class="timeline-content">
        <h3>Phase 2</h3>
        <p>{{$t('section4.item2')}}</p>
      </div>
    </div>

    <div class="timeline-block timeline-block-right">
      <div class="marker"></div>
      <div class="timeline-content">
        <h3>Phase 3</h3>
        <p>{{$t('section4.item3')}}</p>
      </div>
    </div>

    <div class="timeline-block timeline-block-left">
      <div class="marker"></div>
      <div class="timeline-content">
        <!-- <h3>2021&#x200E;.Q1</h3> -->
        <h3>Phase 4</h3>
        <p>{{$t('section4.item4')}}</p>
      </div>
    </div>

    <div class="timeline-block timeline-block-right">
      <div class="marker"></div>
      <div class="timeline-content">
        <h3>Phase 5</h3>
        <p>{{$t('section4.item5')}}</p>
      </div>
    </div>

    <div class="timeline-block timeline-block-left">
      <div class="marker"></div>
      <div class="timeline-content">
        <h3>Phase 6</h3>
        <p>{{$t('section4.item6')}}</p>
      </div>
    </div>

    <div class="timeline-block timeline-block-right">
      <div class="marker"></div>
      <div class="timeline-content">
        <h3>Phase 7</h3>
        <p>{{$t('section4.item7')}}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="less" scoped>

.timeline-container {
  width: 80%;
  padding: 50px 0;
  margin: 50px auto;
  position: relative;
  overflow: hidden;
  &:before {
    content: '';
    position: absolute;
    top: 0;
    left: 50%;
    margin-left: -1px;
    width: 2px;
    height: 100%;
    background: #34d2ec;
    z-index: 1;
  }
}

.timeline-block {
  width: -webkit-calc(50% + 8px);
  width: -moz-calc(50% + 8px);
  width: calc(50% + 8px);
  display: -webkit-box;
  display: -webkit-flex;
  display: -moz-box;
  display: flex;
  -webkit-box-pack: justify;
  -webkit-justify-content: space-between;
  -moz-box-pack: justify;
  justify-content: space-between;
  clear: both;
}

.timeline-block-right {
  float: right;
}

.timeline-block-left {
  float: left;
  direction: rtl;
}

.marker {
  width: 16px;
  height: 16px;
  border-radius: 50%;
  background: #34d2ec;
  margin-top: 10px;
  z-index: 9999;
}

.timeline-content {
  width: 95%;
  padding: 35px 15px;
  color: #fff;
  h3 {
    margin-top: 5px;
    margin-bottom: 5px;
    font-size: 28px;
    font-weight: 600;
    line-height: 40px;
  }
  p {
    font-size: 16px;
    word-spacing: 1px;
  }
}

@media screen and (max-width: 768px) {
  .timeline-container:before {
    left: 8px;
    width: 2px;
  }
  .timeline-block {
    width: 100%;
    margin-bottom: 30px;
  }
  .timeline-block-right {
    float: none;
  }

  .timeline-block-left {
    float: none;
    direction: ltr;
  }
}
</style>