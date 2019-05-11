---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-peoplesoft-enterprise/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 7f8c87e4d29b06b46b559dccf18c3e1038a34fae
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332119"
---
# <a name="import-binding-files"></a>バインド ファイルをインポートします。

## <a name="overview"></a>概要
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用してバインド ファイルをインポートする前に、以下の項目について確認してください。  
  
-   CLASSPATH が PeopleSoft 固有のファイルの特定の場所を指している。 新しいコンピュータで、これらのファイルの場所が同じであることを確認します。同じでない場合は、バインド ファイルを編集します。  
  
-   新しいコンピュータで、応答用のフォルダが存在し、同じである。同じでない場合は、バインド ファイルを編集します。  
  
-   PeopleSoft Enterprise システム パスワードは、構成に存在する場合、として保存されます * * *、バインド ファイルにします。 
  
> [!NOTE]
>  展開すると、受信場所の構成が上書きされます。 バインド ファイルとアセンブリをターゲット コンピューターに展開すると、送信ポートと受信場所が、インポートされた XML バインド ファイルの送信ポートと受信場所に置き換えられます。  
  
 バインド ファイルをインポートする方法の詳細な手順で「どのようにインポート グループにバインドする、BizTalk」のトピックを参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ドキュメント。  
  
## <a name="clean-the-target-computer"></a>ターゲット コンピューターをクリーニングします。  
新しいアプリケーションをデプロイするためのターゲット コンピューターのクリーニング、送信ポートを削除する受信場所をオーケストレーションにバインドされます。  
  
Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] がターゲット コンピューターにインストールされていない場合は、次のスクリプトを実行してポートを削除することができます。  
  
**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Port\VBScript\RemoveSendPort.vbs を送信します。**  
  
**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Port\VBScript\RemoveReceivePort.vbs の受信**  
  
たとえば、コマンド プロンプトで次のように実行します。  
  
**cscript RemoveSendPort.vbs\<送信ポートの名前\>**  
  
