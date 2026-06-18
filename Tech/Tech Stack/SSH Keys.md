ssh-keygen -t ed25519 -C "airon.juan207@gmail.com"

Fedora needs to run a background program called the SSH Agent to manage your key automatically across all terminal tabs. Run these two commands:
eval "$(ssh-agent -s)"

ssh-add ~/.ssh/id_ed25519
Identity added: /home/airon_juan/.ssh/id_ed25519 (airon.juan207@gmail.com)

Print your public lock code onto your screen. Highlight the entire line of text that pops up and copy it to your clipboard.
cat ~/.ssh/id_ed25519.pub

Switch Your Project Link to SSHRun this command inside your ~/Projects/obsidian-vault folder. This tells Git to use your secure SSH connection instead of the web link: