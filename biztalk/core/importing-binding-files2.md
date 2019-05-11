---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: d21d4eaf70948d304564d64379ebd834e89df4ce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382498"
---
# <a name="importing-binding-files"></a>バインド ファイルのインポート
このトピックでは、BizTalk Adapter for JD Edwards EnterpriseOne の展開時のインポート プロセスについて説明します。 バインド ファイルとアセンブリをターゲット コンピューターに再展開すると、送信ポートと受信場所が、再インポートされた XML バインド ファイルの送信ポートと受信場所に置き換えられます。  
  
### <a name="to-clean-the-target-computer"></a>ターゲット コンピューターをクリーニングするには  
  
- 送信ポートを削除して、受信、オーケストレーションにバインドされている場所。  
  
   Visual Studio がターゲット コンピューターにインストールされていない場合は、次のスクリプトを実行してポートを削除することができます。  
  
   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\  
  
   Remove Send Port\VBScript\RemoveSendPort.vbs  
  
   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\  
  
   Remove Receive Port\VBScript\RemoveReceivePort.vbs  
  
   たとえば、コマンド プロンプトで、次のコマンドを実行します。  
  
   **cscript RemoveSendPort.vbs\<送信ポートの名前\>**  
  
## <a name="see-also"></a>参照  
 [インポートの JD Edwards EnterpriseOne のアプリ](../core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone.md)