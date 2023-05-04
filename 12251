let timer;
const hoursInput = document.getElementById('hours');
const minutesInput = document.getElementById('minutes');
const secondsInput = document.getElementById('seconds');
const startButton = document.getElementById('start');
const stopButton = document.getElementById('stop');
const sound = new Audio('path/to/sound.mp3');

startButton.addEventListener('click', () => {
  const totalSeconds = (parseInt(hoursInput.value) || 0) * 3600 + (parseInt(minutesInput.value) || 0) * 60 + (parseInt(secondsInput.value) || 0);
  if (totalSeconds > 0) {
    startTimer(totalSeconds);
  }
});

stopButton.addEventListener('click', () => {
  stopTimer();
});

function startTimer(totalSeconds) {
  const endTime = Date.now() + totalSeconds * 1000;
  timer = setInterval(() => {
    const remainingTime = Math.max(Math.floor((endTime - Date.now()) / 1000), 0);
    const remainingHours = Math.floor(remainingTime / 3600);
    const remainingMinutes = Math.floor((remainingTime % 3600) / 60);
    const remainingSeconds = remainingTime % 60;
    hoursInput.value = remainingHours.toString().padStart(2, '0');
    minutesInput.value = remainingMinutes.toString().padStart(2, '0');
    secondsInput.value = remainingSeconds.toString().padStart(2, '0');
    if (remainingTime === 0) {
      clearInterval(timer);
      sound.play();
      window.alert('Timer expired!');
    }
  }, 1000);
}

function stopTimer() {
  clearInterval(timer);
  hoursInput.value = '';
  minutesInput.value = '';
  secondsInput.value = '';
}
