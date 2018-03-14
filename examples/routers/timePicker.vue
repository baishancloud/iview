<template>
    <Row>
        <Col span="12">
            <TimePicker
                :disabled-hours="[1,5,10]"
                :disabled-minutes="[0,10,20]"
                placeholder="Select time"
                style="width: 168px"></TimePicker>
        </Col>
        <Col span="12">
            <TimePicker
                hide-disabled-options
                :disabled-hours="[1,5,10]"
                :disabled-minutes="[0,10,20]"
                placeholder="Select time"
                style="width: 168px"></TimePicker>
        </Col>
    </Row>
</template>
<script>
    export default {

    }
</script>