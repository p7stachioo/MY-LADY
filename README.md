
            noClickCount = 0;
            noCounter.classList.add('hidden');
            
            container.classList.add('hidden');
            success.classList.remove('hidden');
            
            // Confetti effect
            for (let i = 0; i < 50; i++) {
                const confetti = document.createElement('div');
                confetti.style.position = 'absolute';
                confetti.style.width = '10px';
                confetti.style.height = '10px';
                confetti.style.backgroundColor = ['#f00', '#0f0', '#00f', '#ff0', '#f0f'][Math.floor(Math.random() * 5)];
                confetti.style.borderRadius = '50%';
                confetti.style.left = Math.random() * 100 + 'vw';
                confetti.style.top = '-10px';
                confetti.style.zIndex = '1000';
                document.body.appendChild(confetti);
                
                const animation = confetti.animate([
                    { top: '-10px', opacity: 1 },
                    { top: '100vh', opacity: 0 }
                ], {
                    duration: Math.random() * 3000 + 2000,
                    easing: 'cubic-bezier(0.1, 0.8, 0.9, 1)'
                });
                
                animation.onfinish = () => confetti.remove();
            }
        });
        
        // Initialize feather icons
        feather.replace();
        
        // Update share link with current URL
        document.getElementById('shareLink').value = window.location.href;
    </script>
</body>
</html>
