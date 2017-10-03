---
title: "Files1 のバインドのインポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- binding files, importing
- CLASSPATH environment variable
- importing binding files
- cleaning target computer
ms.assetid: b2a9b19b-2d3d-45ea-bd92-a2501791b86a
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12fca64580b692f01834b48085aa2d88085fb743
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="importing-binding-files"></a>バインド ファイルのインポート
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を使用してバインド ファイルをインポートする前に、以下の項目について確認してください。  
  
-   CLASSPATH が PeopleSoft 固有のファイルの特定の場所を指している。 新しいコンピュータで、これらのファイルの場所が同じであることを確認します。同じでない場合は、バインド ファイルを編集します。  
  
-   新しいコンピュータで、応答用のフォルダが存在し、同じである。同じでない場合は、バインド ファイルを編集します。  
  
-   PeopleSoft Enterprise システム パスワードが構成に存在する場合、パスワードが ***** としてバインド ファイルに保存されている。 詳細については、次を参照してください。[展開の制限事項](../core/deployment-limitations3.md)です。  
  
> [!NOTE]
>  展開すると、受信場所の構成が上書きされます。 バインド ファイルとアセンブリを展開先のコンピュータに展開すると、送信ポートと受信場所が、インポートされた XML バインド ファイルの送信ポートと受信場所に置き換えられます。  
  
 バインド ファイルをインポートする手順については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ドキュメントの「BizTalk グループにバインドをインポートする方法」を参照してください。  
  
## <a name="cleaning-the-target-computer"></a>展開先のコンピューターのクリーニング  
 展開先のコンピュータをクリーニングして新しいアプリケーションを展開するには、次の手順に従います。  
  
#### <a name="to-clean-the-target-computer"></a>展開先のコンピューターをクリーニングするには  
  
-   送信ポートを削除して、受信場所、オーケストレーションにバインドします。  
  
     Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] が展開先のコンピューターにインストールされていない場合は、次のスクリプトを実行してポートを削除することができます。  
  
     **\<Microsoft BizTalk Server > \SDK\Samples\Admin\WMI\Remove Port\VBScript\RemoveSendPort.vbs の送信**  
  
     **\<Microsoft BizTalk Server > \SDK\Samples\Admin\WMI\Remove Port\VBScript\RemoveReceivePort.vbs の受信**  
  
     たとえば、コマンド プロンプトで次のように実行します。  
  
     **cscript RemoveSendPort.vbs\<送信ポートの名前 >**  
  
## <a name="see-also"></a>参照  
 [ポートとアセンブリの展開](../core/deploying-ports-and-assemblies5.md)