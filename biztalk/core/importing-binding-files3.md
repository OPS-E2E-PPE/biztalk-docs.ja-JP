---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 920693d0e3ff02b00d8675261db3050f8866b234
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332169"
---
# <a name="importing-binding-files"></a>バインド ファイルのインポート

## <a name="overview"></a>概要
BizTalk Server を使用してバインド ファイルをインポートする前に、次のことを確認します。  
  
-   CLASSPATH が JD Edwards 固有のファイルの特定の場所を指している。 新しいコンピューターで、これらのファイルの場所が同じであることを確認します。同じでない場合は、バインド ファイルを編集します。  
  
-   新しいコンピューターに、応答用の同じフォルダーが存在する。同じでない場合は、バインド ファイルを編集します。  
  
-   JD Edwards システム パスワードが構成に存在する場合、パスワードが ***** としてバインド ファイルに保存されている。 
  
> [!NOTE]
>  展開には、受信場所の構成が上書きされます。 バインド ファイルとアセンブリをターゲット コンピューターに展開すると、送信ポートと受信場所が、インポートされた XML バインド ファイルの送信ポートと受信場所に置き換えられます。  
  
## <a name="import-the-binding-files"></a>バインド ファイルをインポートします。  
  
1.  **開始**メニューで、 **Program Files**、 をポイント**Microsoft BizTalk Server**、順にクリックします**BizTalk Server 管理**BizTalk Server 管理コンソールを開始します。  
  
2.  BizTalk Server 管理コンソールを展開し、 **BizTalk グループ**、順に展開**アプリケーション**します。  
  
3.  目的のアプリケーションを右クリックし、 をポイント**インポート**、 をクリックし、**バインド**します。  
  
4.  **バインドのインポート**ダイアログ ボックスで、参照し、バインド ファイルを選択してクリックして**オープン**します。  
  
## <a name="cleaning-the-target-computer"></a>ターゲット コンピューターのクリーニング  
送信ポートとオーケストレーションにバインドされている受信場所を削除します。  
  
## <a name="see-also"></a>参照  
 [BizTalk 管理コンソールに、アイテムを追加します。](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)   
 [インポートの JD Edwards OneWorld アプリ](deploying-biztalk-adapter-for-jd-edwards-oneworld.md)