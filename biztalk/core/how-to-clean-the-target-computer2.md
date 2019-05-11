---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-tibco-enterprise-message-service/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 936f25f9dda62cf881b4539a0eee475118294f95
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342386"
---
# <a name="how-to-clean-the-target-computer"></a>対象のコンピューターをクリーニングする方法
展開には、受信場所の構成が上書きされます。 バインド ファイル (およびアセンブリ) をターゲット コンピューターに展開すると、送信ポートと受信場所が、インポートされた XML バインド ファイルの送信ポートと受信場所に置き換えられます。  
  
### <a name="to-clean-the-target-computer"></a>ターゲット コンピューターをクリーニングするには  
  
-   送信ポートを削除して、受信場所がオーケストレーションにバインドされています。  
  
     Microsoft Visual Studio がターゲット コンピューターにインストールされていない場合は、次のスクリプトを実行してポートを削除できます。  
  
     \<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Port\VBScript\RemoveSendPort.vbs を送信します。  
  
     \<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Port\VBScript\RemoveReceivePort.vbs の受信  
  
     たとえば、コマンド プロンプトで次のように実行します。  
  
     **cscript RemoveSendPort.vbs\<送信ポートの名前\>**  
  
