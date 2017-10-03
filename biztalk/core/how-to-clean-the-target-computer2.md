---
title: "ターゲット Computer2 をクリーニングする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: cleaning target computer
ms.assetid: 0d25930e-0bee-4658-80e7-4a1ab4a8131d
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b15614af9a42489693d535896245254208379d76
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-clean-the-target-computer"></a>対象となるコンピューターをクリーニングする方法
展開には、受信場所の構成が上書きされます。 バインド ファイル (およびアセンブリ) を展開先のコンピューターに展開すると、送信ポートと受信場所が、インポートされた XML バインド ファイルの送信ポートと受信場所に置き換えられます。  
  
### <a name="to-clean-the-target-computer"></a>展開先のコンピューターをクリーニングするには  
  
-   送信ポートを削除して、受信場所をオーケストレーションにバインドされています。  
  
     Microsoft Visual Studio が展開先のコンピューターにインストールされていない場合は、次のスクリプトを実行してポートを削除できます。  
  
     \<Microsoft BizTalk Server > \SDK\Samples\Admin\WMI\Remove Port\VBScript\RemoveSendPort.vbs の送信  
  
     \<Microsoft BizTalk Server > \SDK\Samples\Admin\WMI\Remove Port\VBScript\RemoveReceivePort.vbs の受信  
  
     たとえば、コマンド プロンプトで次のように実行します。  
  
     **cscript RemoveSendPort.vbs\<送信ポートの名前 >**  
  
## <a name="see-also"></a>参照  
 [ポートとアセンブリの展開](../core/deploying-ports-and-assemblies2.md)