---
title: IntelliSense を使用して、インターセプター構成ファイルを作成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 349ea1bf-a5d1-4464-bf4b-d8746c622377
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 502b9f1d213a9440bb19820f9998604267045a44
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396863"
---
# <a name="using-intellisense-to-create-an-interceptor-configuration-file"></a>IntelliSense を使用したインターセプター構成ファイルの作成
IntelliSense およびスキーマ検証を使用する[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]概略的に有効なインターセプター構成ファイルを作成するお手伝いをします。 BAM 管理ユーティリティでは、基本的なインターセプター構成スキーマに対してインターセプター構成ファイルを検証し、ファイルが有効でない場合、スキーマをデプロイしません。 ファイルには、基本的なインターセプター構成スキーマに対して検証が成功した場合は、ようなテクノロジに固有のスキーマに対して検証、[!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)]スキーマまたは[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)]スキーマ中に実行時間とインターセプトはないエラーが発生した場合発生します。 スキーマの検証を使用してこれらのエラーを回避できます[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]インターセプタ構成ファイルを作成するときにします。  
  
> [!NOTE]
>  サンプルの BAM インターセプタ構成 XSD ファイルは、SDK ファイルと共にインストールされます。 見つかります[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \samples\bam\interceptorxsds:  
> 
> - CommonInterceptorConfiguration.xsd  
>   -   WcfInterceptorConfiguration.xsd  
>   -   WorkflowInterceptorConfiguration.xsd  
  
### <a name="to-obtain-a-copy-of-the-interceptor-schemas"></a>インターセプタ スキーマのコピーを入手するには  
  
1. メモ帳または別のテキスト エディターを開きます。  
  
2. 移動し、[インターセプタ構成スキーマ](../core/interceptor-configuration-schema.md)トピック。  
  
3. 開いているテキスト エディターで新しいドキュメントに内容を貼り付けるし、名前を使用してテキスト ファイルとして保存します**CommonInterceptorConfiguration.xsd** (または、独自に選択のいずれか) をハード_ディスクにします。  
  
4. これらの手順を繰り返します、[!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)]スキーマと[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)]ファイル名を使用してスキーマ トピック**WorkflowInterceptorConfiguration.xsd**と**WcfInterceptorConfiguration.xsd**または名独自の次のように選択します。  
  
### <a name="to-use-intellisense-with-your-interceptor-configuration-file"></a>インターセプタ構成ファイルで IntelliSense を使用するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]を開きます。  
  
2. をクリックして**ファイル**、 をクリックして**新規**、 をクリックし、**ファイル**します。  
  
3. **新しいファイル**ダイアログ ボックスで、 **XML ファイル** をクリックし、**オープン**します。  
  
4. プロパティ ペインを表示、編集ウィンドウを右クリックし、をクリックして**プロパティ**します。  
  
5. プロパティ ペインで次のようにクリックします**スキーマ**、クリックして、省略記号 (**...**).  
  
6. **XML スキーマ**ダイアログ ボックスで、をクリックして**追加**クリックし、スキーマの場所に移動します**CommonInterceptorConfiguration.xsd**と**WcfInterceptorConfiguration.xsd**で作業している場合、[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)]インターセプター構成ファイル、または**WorkflowInterceptorConfiguration.xsd**で作業している場合、 [!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)]インターセプター構成ファイル。  
  
   > [!NOTE]
   >  別の名前を使用して、ファイルを保存した場合は、それらのファイルを選択します。  
  
7. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] これで開かれたときに、インターセプタ構成ファイルを検証を作成し、ファイルを変更する際に IntelliSense のヘルプを提供します。  
  
## <a name="see-also"></a>参照  
 [Windows Workflow Foundation スキーマ](../core/windows-workflow-foundation-schema.md)   
 [Windows Communication Foundation スキーマ](../core/windows-communication-foundation-schema.md)