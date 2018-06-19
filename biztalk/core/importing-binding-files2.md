---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 7dbc9ef8624404b9fa7bdcb7b6a21b2d2a4c69f2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971248"
---
# <a name="importing-binding-files"></a>バインド ファイルのインポート
このトピックでは、BizTalk Adapter for JD Edwards EnterpriseOne の展開時のインポート プロセスについて説明します。 バインド ファイルとアセンブリを展開先のコンピューターに再展開すると、送信ポートと受信場所が、再インポートされた XML バインド ファイルの送信ポートと受信場所に置き換えられます。  
  
### <a name="to-clean-the-target-computer"></a>展開先のコンピューターをクリーニングするには  
  
-   送信ポートを削除して、受信場所、オーケストレーションにバインドします。  
  
     Visual Studio が展開先のコンピューターにインストールされていない場合は、次のスクリプトを実行してポートを削除することができます。  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\  
  
     Remove Send Port\VBScript\RemoveSendPort.vbs  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\  
  
     Remove Receive Port\VBScript\RemoveReceivePort.vbs  
  
     たとえば、コマンド プロンプトで、次のコマンドを実行します。  
  
     **cscript RemoveSendPort.vbs\<送信ポートの名前\>**  
  
## <a name="see-also"></a>参照  
 [インポート JD Edwards EnterpriseOne アプリケーション](../core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone.md)