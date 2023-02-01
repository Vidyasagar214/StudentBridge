<template>
       <div class="stepper-box">
        <div class="container-fluid">
                <div class="steps">
                    <progress id="progress" value=0 max=100 ></progress>
                    
                    <div class="step-item d-flex flex-column align-items-center">
                        <div class="step-button ">
                            <font-awesome-icon :icon="['fa', 'circle-check']" class="stepper-icon completed"/>
                        </div>
                        <NuxtLink to="/dashboard/ideation"> <div class="step-title completed">
                            Ideation
                        </div></NuxtLink>
                    </div>
                    
                    <div class="step-item d-flex flex-column align-items-center">
                        <div class="step-button " >
                            <font-awesome-icon :icon="['fa', 'circle-check']" class="stepper-icon completed"/>
                        </div>
                        <NuxtLink to="/dashboard/creative"> <div class="step-title completed">
                            Creative
                        </div></NuxtLink>
                    </div>
                    <div class="step-item d-flex flex-column align-items-center">
                        <div class="step-button " >
                            <font-awesome-icon :icon="['fa', 'circle-check']" class="stepper-icon completed"/>
                        </div>
                        <div class="step-title completed">
                            Talent selection
                        </div>
                    </div>
                    <div class="step-item d-flex flex-column align-items-center">
                        <div class="step-button" >
                            <font-awesome-icon :icon="['fa', 'circle-dot']" class="stepper-icon pending"/>
                        </div>
                        <NuxtLink to="/dashboard/scheduling"><div class="step-title pending">
                            Scheduling
                        </div></NuxtLink>
                    </div>
                    <div class="step-item d-flex flex-column align-items-center">
                        <div class="step-button " >
                            <font-awesome-icon :icon="['fa', 'circle-dot']" class="stepper-icon"/>
                        </div>
                        <div class="step-title">
                           Filming
                        </div>
                    </div>
                    <div class="step-item d-flex flex-column align-items-center">
                        <div class="step-button " >
                            <font-awesome-icon :icon="['fa', 'circle-dot']" class="stepper-icon"/>
                        </div>
                        <div class="step-title ">
                           Upload and Review
                        </div>
                    </div>
                </div>
                
            </div>
       
        </div>
</template>

<script >


</script>

<style >

.stepper-box{
  width:100%;
  height: 80px;
  border-bottom: 2px solid #EDEFF2;
  display: flex;
  align-items: center;
  justify-content: center;
}

.steps {
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: relative;
}

.step-button {
    width: 30px;
    height: 30px;
    border-radius: 50%;
    border: none;
    background-color:rgb(255, 255, 255);
    
}

.stepper-icon{
    width: 30px;
    height: 30px;
    color:#C3CAD9;
}
.step-title{
    font-size: 14px;
    font-weight: 500;
    color: #C3CAD9;
}
.pending{
    color: #1C676C;
}
.completed{
    color: rgb(180, 212, 90) !important;
}

.step-item {
    z-index: 10;
    text-align: center;
}

#progress {
    position: absolute;
    width: 91% !important;
    z-index: 5;
    height: 3px;
    margin-left: 18px;
    margin-bottom: 18px;
    background-color:#C3CAD9;
}

/* to customize progress bar */
/* #progress::-webkit-progress-value {
    background-color: green;
    transition: .5s ease;
} */

#progress::-webkit-progress-bar {
    background-color:#C3CAD9;

}

</style>