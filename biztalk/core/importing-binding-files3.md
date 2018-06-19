---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 5c5cce40f3fbeb580ec7ba854d02cb243e1742b4
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013465"
---
# <a name="importing-binding-files"></a>バインド ファイルのインポート

## <a name="overview"></a>概要
バインド ファイルをインポートする BizTalk Server を使用する前に、次の操作を確認します。  
  
-   CLASSPATH が JD Edwards 固有のファイルの特定の場所を指している。 新しいコンピューターで、これらのファイルの場所が同じであることを確認します。同じでない場合は、バインド ファイルを編集します。  
  
-   新しいコンピューターに、応答用の同じフォルダーが存在する。同じでない場合は、バインド ファイルを編集します。  
  
-   JD Edwards システム パスワードが構成に存在する場合、パスワードが ***** としてバインド ファイルに保存されている。 
  
> [!NOTE]
>  展開には、受信場所の構成が上書きされます。 バインド ファイルとアセンブリを展開先のコンピューターに展開すると、送信ポートと受信場所が、インポートされた XML バインド ファイルの送信ポートと受信場所に置き換えられます。  
  
## <a name="import-the-binding-files"></a>バインド ファイルをインポートします。  
  
1.  **開始** メニューのをポイント**Program Files**、 をポイント**Microsoft BizTalk Server**、順にクリック**BizTalk Server 管理コンソール**BizTalk Server 管理コンソールを開始します。  
  
2.  BizTalk Server 管理コンソールを展開し、 **BizTalk グループ**の順に展開および**アプリケーション**です。  
  
3.  目的のアプリケーションを右クリックし、順にポイント**インポート**、順にクリック**バインド**です。  
  
4.  **バインドのインポート**ダイアログ ボックスで、参照し、バインド ファイルを選択してクリックして**開く**です。  
  
## <a name="cleaning-the-target-computer"></a>展開先のコンピューターのクリーニング  
送信ポートおよびオーケストレーションにバインドされている受信場所を削除します。  
  
## <a name="see-also"></a>参照  
 [BizTalk 管理コンソールに、アイテムを追加します。](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)   
 [インポート JD Edwards OneWorld アプリ](deploying-biztalk-adapter-for-jd-edwards-oneworld.md)