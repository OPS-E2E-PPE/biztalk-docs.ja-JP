---
redirect_url: /biztalk/core/adding-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: e2101cee6e82283984bd0e830a583a96613d21b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385430"
---
# <a name="how-to-create-send-ports-for-jd-edwards-oneworld"></a>JD Edwards OneWorld 用送信ポートの作成方法
送信ポートを作成するのにには、次の手順を使用します。  
  
### <a name="to-create-a-send-port"></a>送信ポートを作成するには  
  
1.  BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、順に移動します、必要なアプリケーションです。  
  
2.  右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な送信請求-応答送信ポート**します。  
  
    > [!NOTE]
    >  使用することも**静的な一方向ポート**します。  
  
3.  **送信ポートのプロパティ** ダイアログ ボックスで、**名前**フィールドに、送信ポートの名前を入力 (たとえば、「 **SendToJDE**。)  
  
4.  **型**ドロップダウン リストで、 **[jdeoneworld]** します。  
  
5.  **URI**ドロップダウン リストで、送信ハンドラーを選択します。  
  
6.  **[OK]** をクリックします。  
  
