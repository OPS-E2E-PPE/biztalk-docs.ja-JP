---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: db28e1db8a0f2d4149e0539e2bce195cd91b1279
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973987"
---
# <a name="importing-binding-files"></a>バインド ファイルのインポート
このトピックでは、BizTalk Adapter for JD Edwards EnterpriseOne の展開時のインポート プロセスについて説明します。 バインド ファイルとアセンブリを展開先のコンピューターに再展開すると、送信ポートと受信場所が、再インポートされた XML バインド ファイルの送信ポートと受信場所に置き換えられます。  
  
### <a name="to-clean-the-target-computer"></a>展開先のコンピューターをクリーニングするには  
  
- 送信ポートを削除して、受信、オーケストレーションにバインドされている場所。  
  
   Visual Studio が展開先のコンピューターにインストールされていない場合は、次のスクリプトを実行してポートを削除することができます。  
  
   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\  
  
   Remove Send Port\VBScript\RemoveSendPort.vbs  
  
   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\  
  
   Remove Receive Port\VBScript\RemoveReceivePort.vbs  
  
   たとえば、コマンド プロンプトで、次のコマンドを実行します。  
  
   **cscript RemoveSendPort.vbs\<送信ポートの名前\>**  
  
## <a name="see-also"></a>参照  
 [インポートの JD Edwards EnterpriseOne のアプリ](../core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone.md)