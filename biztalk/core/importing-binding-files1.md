---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-peoplesoft-enterprise/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 8a2b78ee2e8ec75c6ce83a8b78d1e779f012f324
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
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
  
**\<Microsoft BizTalk Server > \SDK\Samples\Admin\WMI\Remove Port\VBScript\RemoveSendPort.vbs の送信**  
  
**\<Microsoft BizTalk Server > \SDK\Samples\Admin\WMI\Remove Port\VBScript\RemoveReceivePort.vbs の受信**  
  
たとえば、コマンド プロンプトで次のように実行します。  
  
**cscript RemoveSendPort.vbs\<送信ポートの名前 >**  
  
