<template>
  <div class="phone">
    <header class="call-details">
      <div class="title">
        <CustomText sr>Call with</CustomText>
        <CustomText tag="h3" tb>Niloya Kayıkçı</CustomText>
      </div>
      <div class="date">
        <div>
          <Calendar />
          <CustomText tag="time" sr>7 Oct, Weds</CustomText>
        </div>
        <div>
          <Clock />
          <CustomText tag="time" sr>10:15AM - 10:30AM</CustomText>
        </div>
      </div>
    </header>
    <CustomText class="timezone" sr>Timezone: Europe/Amsterdam</CustomText>
    <section class="video">
      <div class="video-frame">
        <img src="@/assets/video-preview.png" alt="video-preview" />
        <div class="actions">
          <IconButton><Microphone /></IconButton>
          <IconButton><Camera /></IconButton>
          <IconButton><Options /></IconButton>
        </div>
      </div>
      <Input />
    </section>
    <section class="controls">
      <Row text="Camera">
        <Dropdown :list="cameraList" />
      </Row>
      <Row text="Camera">
        <Dropdown :list="cameraList" />
      </Row>
      <Row text="Speaker">
        <Dropdown :list="speakerList" />
      </Row>
      <Row text="Microphone">
        <Dropdown :list="microphoneList" />
      </Row>
      <Row text="Sound Test">
        <Button>Play Sound</Button>
      </Row>
    </section>
    <Button primary full>Join Call</Button>
  </div>
</template>

<script>
import Calendar from '@/icons/calendar.svg';
import Camera from '@/icons/camera.svg';
import Clock from '@/icons/clock.svg';
import Microphone from '@/icons/microphone.svg';
import Options from '@/icons/options.svg';

import IconButton from '@/components/IconButton.vue';
import CustomText from '@/components/CustomText.vue';
import Button from '@/components/Button.vue';
import Input from '@/components/Input.vue';
import Dropdown from '@/components/Dropdown.vue';
import Row from '@/components/Row.vue';
export default {
  name: 'Phone',
  components: {
    CustomText,
    Dropdown,
    Input,
    Button,
    IconButton,
    Row,
    Calendar,
    Camera,
    Clock,
    Microphone,
    Options,
  },
  data() {
    return {
      cameraList: [
        { key: 1, value: 'Facetime HD Camera' },
        { key: 2, value: 'Built in Camera' },
      ],
      speakerList: [
        { key: 1, value: 'Built-in Output (Headphone)' },
        { key: 2, value: 'Built in Speaker' },
      ],
      microphoneList: [
        { key: 1, value: 'Built-in Microphone (E...)' },
        { key: 2, value: 'Built in Microphone' },
      ],
    };
  },
};
</script>

<style lang="scss">
.phone {
  width: 384px;
  height: 867px;
  margin-left: auto;
  margin-right: auto;
  padding: 32px 24px;
  background-color: $white;
  text-align: center;
  box-shadow: 0px 10px 30px rgba(0, 0, 0, 0.1);
  border-radius: 16px;

  & > *:not(:last-child) {
    margin-bottom: 24px;
  }

  header.call-details {
    .title {
      margin-bottom: 16px;
      span {
        color: $primary;
        margin-bottom: 4px;
      }
    }
    .date {
      padding: 16px;
      border: 1px solid $grey40;
      border-radius: 8px;
      display: flex;
      align-items: center;
      justify-content: space-between;

      & > div {
        display: flex;
        align-items: center;
        svg {
          color: $primary;
          margin-right: 8px;
          font-size: 18px;
        }
      }
    }
  }

  .timezone {
    color: $grey80;
    display: inline-block;
  }

  .video {
    &-frame {
      position: relative;
      height: 192px;
      display: flex;
      justify-content: center;
      margin-bottom: 16px;

      img {
        position: absolute;
        left: 0;
        top: 0;
        bottom: 0;
        right: 0;
        width: 100%;
        height: 100%;
        background-color: $grey40;
        border-radius: 8px;
        object-fit: cover;
      }
      .actions {
        margin-top: auto;
        margin-bottom: 12px;
        position: relative;

        & > *:not(:last-child) {
          margin-right: 12px;
        }
      }
    }
  }
}
</style>
