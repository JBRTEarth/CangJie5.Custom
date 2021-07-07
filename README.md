# 快選功能尚待完成……
# CangJie5.Custom
	# 一、目前僅提供中州韻輸入法框架的yaml檔，修改檔基於原作者Jackchows的cangjie5_tc.dict.yaml。
		# https://rime.im/
		# https://github.com/Jackchows/Cangjie5
	# 二、未來可能改用lex檔，基於原作者Arthurmcarthur的微軟倉頡碼表編輯器。
		# 已用Jackchows的lex檔測試，環境，Win10Homex64.20h2(19042.985)、安全軟體COMODO，稍為延遲幾毫秒，待研究。
		# https://github.com/Arthurmcarthur/MicrosoftCangjieTool
20210524
	
# 零、結構（20200812）：
	# Keyboard Layout: qwerty.
	# 簡碼（參考：ROC重編國語辭典第五版、PRC雙拼智能ABC、朱邦復漢字基因字典），
	# 內容：注音、聲調、常用標點符號、常用字簡碼。
	# 「倉三」有不少異體字，之後考慮增加倉頡三代補完計畫碼表（倉三原碼，部首筆劃）。
#
# 壹、注音，雙拼佈局（定音ｚ鍵）：
	# 「聲母」，漢拼字首──ｚ鍵；
	# 「韻母」，ｚ鍵──漢拼原形（ㄝㄜ重碼，ㄝ：ｚｅｅ）；
	# 「介母」，ㄧ：yz、ㄨ：wz、ㄩ：zu。
#
# 貳、聲調，自設五鍵（定音ｚｘ鍵）：
	# 「聲調」，ｚｘ鍵──「金、紐、月、鉤、橫」（cvbnm），
	# 陰平「金，ˉ」；陽平「紐，ˊ」；輕聲「月，˙」；上聲「鉤，ˇ」；去聲「橫，ˋ」。
#
# 參、常用標點符號，共十九鍵：
	# 盲打凸點位置水平一排九鍵、與其上一排十鍵。
#
# 肆、常用字簡碼，依照倉五碼（結合「複合字首」倉三碼），設大字根、設快選碼：
	# 肆一、「找字」功能，大五碼5401個常用字，字母順序，頭尾共二碼。
	# 肆二、「快打」功能，教育部4808個常用字，教育部序，篩選共三碼，快選──uio，二三四；jkl，五六七。
	# （常用字一至二碼字已刪去。）
    # 肆二一、篩選整體字，刪第三碼。
      # 字形筆畫交連（例，焉）；
      # 形勢完整（例，噩）；
      # 複合字、難字、特殊字（例，麻、⺽、柬）。
      # 歸納：
        # 單純之「丨、㇒」與其「上形」相連（例，卑、泉，㇒以「中間」為準）
        # 「八、儿、⼉」與其「上部」相連（例，夔、兜、西）
        # 「、」附屬於整個字形（例，兔）
        # 「乛、⺈」與其「下形」相連（例，及、角）
    # 肆二二、篩選組合字，字首取一碼（取尾碼），字身取二碼。
      # 字身為整體字────刪次碼（如，飛、啄）。
      # 字身為組合字────如下：
        # 次字首────刪其頭碼（如，扉、咬）；
        # 　　　　　或刪其碼（如，施、候）；
        # 　　　　　若字身共二碼，復取其碼（如，乾）。
        # 「字形」，出現於置右且單（例，翔；反例，條）；
        # 　　　　　　　　置底且單（例，導；反例，潺）；
        # 　　　　　　　　置右底且單（例，將），只取尾碼。（頻率高，重碼多）
        # 如下：（大字根）
          # 刂、卩、彡、青、吉、侖、奇、合、巾、阝、
          # 隹、攵、欠、殳、皿、石、貝、頁、羽、鳥、
          # 力、寸、子、包、屯、示、主、反、官、全、
          # 蜀、召、丁、瓦、艮、喬、見、相、㐬、式、
          # 斗、羊、乇、才、斤、共、巴、我、馬、目
          # 若字身不足二碼────復取「字首」頭碼（如，列）；
          # 　　　　　　　　　復取「次字首」其碼（如，勞）；
          # 　　　　　　　　　刪「整體字字形」次碼（如，員）；
          # 　　　　　　　　　復取「組合字字形」頭碼（如，哈）。
#
# 題外（雛形）
	# 壹、疊重複形，取重合形，如，
    # 鬻（弜，弓），鉤木橫口月；班（玨，王），橫土點縱；轟（車），交方交；
    # 順（川，丨），縱橫月金；須（彡，丿），斜橫月金；參（厽，厶、彡，丿），點人斜。
	# 貳、同碼字重碼過五，如：鬻、贏，內三角、一線三點、一頂或底點拆法，
    # 剪字：「上或下內三角」，得「四個字形（各點自成一體）」（橫三、頂或底一）。
    # 取碼：內三角點取二碼，橫中點取三碼，
    # 上內三角，取上點頭碼，取右點尾碼；下內三角，取左點頭碼，取下點尾碼。
    # 如，鬻，鉤縱火木；贏，卜鉤月仰金、卜叉月仰金。
# （20200812）
# 20200707
# 常用字三碼倉五第二版方向，
	
	五碼字（2.3）────
		整體字字身：字首取頭尾、字身取尾。
		分體字字身：字首取頭、字身取頭尾。

	四碼字（4、1.3、2.2）────
		整體字，前二與尾
		整體字字身：字首取頭尾、字身取尾；字首一碼、字身取頭尾。例：理，一田土、啄，口一人。
		分體字字身：字首取頭、字身取頭尾；字首一碼、字身取頭尾。例：皓，竹竹口、滅，水戈火。

	例外分體字字身，視作整體字字身：殳、刂、、欠、青、（直直、彡、䖵等等，重合形）、未完
	（口，字身首碼且無相連）
