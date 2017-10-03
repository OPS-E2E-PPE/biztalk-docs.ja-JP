---
title: "IntelliSense を使用して、インターセプター構成ファイルを作成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 349ea1bf-a5d1-4464-bf4b-d8746c622377
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7be3f79545db81a0127fc8d004d71c758069a55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-intellisense-to-create-an-interceptor-configuration-file"></a>IntelliSense を使用したインターセプター構成ファイルの作成
[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の Intellisense およびスキーマ検証を使用して、図式的に有効なインターセプター構成ファイルを構築できます。 BAM 管理ユーティリティは、基本的なインターセプター構成スキーマに対してインターセプター構成ファイルを検証し、ファイルが無効な場合はスキーマを展開しません。 ファイルが基本的なインターセプター構成スキーマに対する検証に合格すると、[!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)] スキーマや [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] スキーマなど、テクノロジ固有のスキーマに対して実行時に検証が行われ、エラーが発生した場合は傍受を行いません。 インターセプター構成ファイルを構築するときに、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のスキーマ検証を使用することで、これらのエラーを回避できます。  
  
> [!NOTE]
>  BAM インターセプタ構成 XSD ファイルのサンプルは、SDK ファイルと共にインストールされます。 このファイルは、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\BAM\InterceptorXSDs にあります。  
>   
>  -   CommonInterceptorConfiguration.xsd  
> -   WcfInterceptorConfiguration.xsd  
> -   WorkflowInterceptorConfiguration.xsd  
  
### <a name="to-obtain-a-copy-of-the-interceptor-schemas"></a>インターセプタ スキーマのコピーを取得するには  
  
1.  メモ帳または任意のテキスト エディタを開きます。  
  
2.  移動し、[インターセプタ構成スキーマ](../core/interceptor-configuration-schema.md)トピックです。  
  
3.  開いているテキスト エディターで、新しいドキュメントにコンテンツを貼り付けるし、名前を使用してテキスト ファイルとしてファイルを保存**CommonInterceptorConfiguration.xsd** (または独自の 1 つ)、ハード ディスクにします。  
  
4.  これらの手順を繰り返します、[!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)]スキーマと[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)]ファイル名を使用してスキーマ トピック**WorkflowInterceptorConfiguration.xsd**と**である WcfInterceptorConfiguration.xsd**または名独自の次のように選択します。  
  
### <a name="to-use-intellisense-with-your-interceptor-configuration-file"></a>インターセプター構成ファイルで Intellisense を使用するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]を開きます。  
  
2.  をクリックして**ファイル**、 をクリックして**新規**、クリックして**ファイル**です。  
  
3.  **新しいファイル**ダイアログ ボックスで、 **XML ファイル** をクリックし、**開く**です。  
  
4.  編集ウィンドウを右クリックし、をクリックしてプロパティ ウィンドウを表示する**プロパティ**です。  
  
5.  プロパティ ウィンドウで、をクリックして**スキーマ**、クリックして、省略記号 (**.**).  
  
6.  **XML スキーマ**ダイアログ ボックスで、をクリックして**追加**クリックし、スキーマの場所に移動し、 **CommonInterceptorConfiguration.xsd**と**ある WcfInterceptorConfiguration.xsd**で作業している場合、[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)]インターセプター構成ファイル、または**WorkflowInterceptorConfiguration.xsd**で作業している場合、 [!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)]インターセプター構成ファイル。  
  
    > [!NOTE]
    >  別の名前でファイルを保存した場合は、その名前を選択します。  
  
7.  インターセプター構成ファイルを開くと [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] によりファイルが検証され、ファイルを作成および変更するときに Intellisense のヘルプが提供されます。  
  
## <a name="see-also"></a>参照  
 [Windows Workflow Foundation スキーマ](../core/windows-workflow-foundation-schema.md)   
 [Windows Communication Foundation スキーマ](../core/windows-communication-foundation-schema.md)