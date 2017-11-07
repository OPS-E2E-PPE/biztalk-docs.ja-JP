---
redirect_url: /biztalk/core/adding-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: d65b87fbcbdaf89289406ae6850b70c605123451
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="how-to-create-send-ports-for-jd-edwards-oneworld"></a>JD Edwards OneWorld 用送信ポートの作成方法
次の手順を使用すると、送信ポートを作成できます。  
  
### <a name="to-create-a-send-port"></a>送信ポートを作成するには  
  
1.  BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**に移動し、必要なアプリケーションです。  
  
2.  右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な送信請求-応答送信ポート**です。  
  
    > [!NOTE]
    >  使用することも**静的な一方向ポート**です。  
  
3.  **送信ポートのプロパティ** ダイアログ ボックスで、**名前**フィールドで、送信ポートの名前を入力 (たとえば、入力**SendToJDE**)。  
  
4.  **型**ドロップダウン リストで、 **[jdeoneworld]**です。  
  
5.  **URI**ドロップダウン リストで、送信ハンドラーを選択します。  
  
6.  **[OK]**をクリックします。  
  
