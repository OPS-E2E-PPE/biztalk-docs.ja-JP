---
redirect_url: /biztalk/core/deploying-biztalk-adapter-for-tibco-enterprise-message-service/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 794ab5e4ed28464ed704d27da05390dad6199224
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-clean-the-target-computer"></a>対象となるコンピューターをクリーニングする方法
展開には、受信場所の構成が上書きされます。 バインド ファイル (およびアセンブリ) を展開先のコンピューターに展開すると、送信ポートと受信場所が、インポートされた XML バインド ファイルの送信ポートと受信場所に置き換えられます。  
  
### <a name="to-clean-the-target-computer"></a>展開先のコンピューターをクリーニングするには  
  
-   送信ポートを削除して、受信場所をオーケストレーションにバインドされています。  
  
     Microsoft Visual Studio が展開先のコンピューターにインストールされていない場合は、次のスクリプトを実行してポートを削除できます。  
  
     \<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Port\VBScript\RemoveSendPort.vbs の送信  
  
     \<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove 受信 Port\VBScript\RemoveReceivePort.vbs  
  
     たとえば、コマンド プロンプトで次のように実行します。  
  
     **cscript RemoveSendPort.vbs\<送信ポートの名前\>**  
  
