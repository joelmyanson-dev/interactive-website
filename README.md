document.addEventListener('DOMContentLoaded', () => {
  const question = document.querySelector('.question');
  const gif = document.querySelector('.gif');
  const yesButton = document.querySelector('.yes-button');
  const noButton = document.querySelector('.no-button');

  if (!question || !gif || !yesButton || !noButton) {
    return;
  }

  yesButton.addEventListener('click', () => {
    question.textContent = 'I know you liked me, you clicked yes!';
    gif.src = 'https://images.unsplash.com/photo-1519681393784-d120267933ba?auto=format&fit=crop&w=800&q=80';
    yesButton.textContent = 'Opening...';

    window.setTimeout(() => {
      window.location.href = 'happy-birthday.html';
    }, 700);
  });

  noButton.addEventListener('mouseover', () => {
    const parentRect = noButton.parentElement?.getBoundingClientRect();
    if (!parentRect) {
      return;
    }

    const maxx = Math.max(0, parentRect.width - noButton.offsetWidth);
    const maxy = Math.max(0, parentRect.height - noButton.offsetHeight);

    const randomX = Math.floor(Math.random() * maxx);
    const randomY = Math.floor(Math.random() * maxy);

    noButton.style.left = randomX + 'px';
    noButton.style.top = randomY + 'px';
  });
});
