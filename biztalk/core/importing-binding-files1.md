---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-peoplesoft-enterprise/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 907c21377a6affd5a99576137a5babaa1626c135
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971304"
---
# <a name="import-binding-files"></a>バインド ファイルをインポートします。

## <a name="overview"></a>概要
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用してバインド ファイルをインポートする前に、以下の項目について確認してください。  
  
-   CLASSPATH が PeopleSoft 固有のファイルの特定の場所を指している。 新しいコンピュータで、これらのファイルの場所が同じであることを確認します。同じでない場合は、バインド ファイルを編集します。  
  
-   新しいコンピュータで、応答用のフォルダが存在し、同じである。同じでない場合は、バインド ファイルを編集します。  
  
-   PeopleSoft Enterprise システム パスワードが構成に存在する場合、パスワードが ***** としてバインド ファイルに保存されている。 
  
> [!NOTE]
>  展開すると、受信場所の構成が上書きされます。 バインド ファイルとアセンブリを展開先のコンピュータに展開すると、送信ポートと受信場所が、インポートされた XML バインド ファイルの送信ポートと受信場所に置き換えられます。  
  
 バインド ファイルをインポートする手順については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ドキュメントの「BizTalk グループにバインドをインポートする方法」を参照してください。  
  
## <a name="clean-the-target-computer"></a>ターゲット コンピューターをクリーニングします。  
新しいアプリケーションの配置ターゲット コンピューターのクリーニング、送信ポートを削除、および受信場所をオーケストレーションにバインドされます。  
  
Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] が展開先のコンピューターにインストールされていない場合は、次のスクリプトを実行してポートを削除することができます。  
  
**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Port\VBScript\RemoveSendPort.vbs の送信**  
  
**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove 受信 Port\VBScript\RemoveReceivePort.vbs**  
  
たとえば、コマンド プロンプトで次のように実行します。  
  
**cscript RemoveSendPort.vbs\<送信ポートの名前\>**  
  
