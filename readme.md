Linux || Mac 系工具配置文件
=========================

启用init_tmux.sh 步骤：

需 'vim ~/.bashrc'。

在.bashrc中添加
 
 	if [ -f ~/.init_tmux ]; then
 	  . ~/.init_tmux
  	fi


