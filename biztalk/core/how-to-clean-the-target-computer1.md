---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-tibco-rendezvous/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 12e8a37da357693b97659c1717ead750e558e62b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018445"
---
# <a name="how-to-clean-the-target-computer"></a>対象のコンピューターをクリーニングする方法
展開には、受信場所の構成が上書きされます。 バインド ファイル (およびアセンブリ) をターゲット コンピューターに展開すると、送信ポートと受信場所が、インポートされた XML バインド ファイルの送信ポートと受信場所に置き換えられます。  
  
### <a name="to-clean-the-target-computer"></a>ターゲット コンピューターをクリーニングするには  
  
- 送信ポートを削除して、受信、オーケストレーションにバインドされている場所。  
  
   Microsoft Visual Studio がターゲット コンピューターにインストールされていない場合は、次のスクリプトを実行してポートを削除できます。  
  
  - [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs  
  
  - [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs  
  
     たとえば、コマンド プロンプトで次のように実行します。  
  
     **cscript RemoveSendPort.vbs\<送信ポートの名前\>**  
  
