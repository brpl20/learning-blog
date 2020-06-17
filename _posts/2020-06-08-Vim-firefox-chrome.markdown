---
title: Vim Firefox Chrome
layout: post
tags: [vim]
---
Não vou conseguir me livrar de aprender VIM, então vamos encarar esse demônio, comecando com alguns conceitos basicos, primeira parte é navegacao. Vou tentar utilizar um plugin de Firefox e Chrome para ir aprendendo os conceitos básicos no 'hjkl' e outras ferramentas de navegacao com o teclado. Vou salvar um arquivo com todos os atalhos que estará sempre a mão e também aqui no blog:

Shortcuts

firefox/vim:
NAVEGAÇÃO

j     baixo
k     cima
l     direita
h     esquerda
gg    Scroll to the top of the page (scrollToTop)
G     Scroll to the bottom of the page (scrollToBottom)
d     Scroll a half page down (scrollPageDown)
u     Scroll a half page up (scrollPageUp)
    Scroll a full page down (scrollFullPageDown)
    Scroll a full page up (scrollFullPageUp)
h     Scroll left (scrollLeft)
l     Scroll right (scrollRight)
r     Reload the page (reload)
yy    Copy the current URL to the clipboard (copyCurrentUrl)
p     Open the clipboard's URL in the current tab (openCopiedUrlInCurrentTab)
P     Open the clipboard's URL in a new tab (openCopiedUrlInNewTab)
i     Enter insert mode (enterInsertMode)
v     Enter visual mode (enterVisualMode)
gi    Focus the first text input on the page (focusInput)
f     Open a link in the current tab (LinkHints.activateMode)
F     Open a link in a new tab (LinkHints.activateModeToOpenInNewTab)
    Open a link in a new tab & switch to it (LinkHints.activateModeToOpenInNewForegroundTab)
gf    Select the next frame on the page (nextFrame)
gF    Select the page's main/top frame (mainFrame)

Using the vomnibar
o     Open URL, bookmark or history entry (Vomnibar.activate)
O     Open URL, bookmark or history entry in a new tab (Vomnibar.activateInNewTab)
b     Open a bookmark (Vomnibar.activateBookmarks)
B     Open a bookmark in a new tab (Vomnibar.activateBookmarksInNewTab)
T     Search through your open tabs (Vomnibar.activateTabSelection)
    Using find
/     Enter find mode (enterFindMode)
n     Cycle forward to the next find match (performFind)
N     Cycle backward to the previous find match (performBackwardsFind)
    Navigating history
H     Go back in history (goBack)
L     Go forward in history (goForward)
    Manipulating tabs
t     Create new tab (createTab)
J, gT     Go one tab left (previousTab)
K, gt     Go one tab right (nextTab)
^     Go to previously-visited tab (visitPreviousTab)
g0    Go to the first tab (firstTab)
g$    Go to the last tab (lastTab)
yt    Duplicate current tab (duplicateTab)
<a-p>     Pin or unpin current tab (togglePinTab)
<a-m>     Mute or unmute current tab (toggleMuteTab)
x     Close current tab (removeTab)
X     Restore closed tab (restoreTab)
    Miscellaneous
?     Show help (showHelp)
