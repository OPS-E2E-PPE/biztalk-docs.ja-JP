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
ms.openlocfilehash: 1d6df002c51bbcc51a3cb714e389a0f453a0693c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011355"
---
# <a name="using-intellisense-to-create-an-interceptor-configuration-file"></a>IntelliSense を使用したインターセプター構成ファイルの作成
[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の Intellisense およびスキーマ検証を使用して、図式的に有効なインターセプター構成ファイルを構築できます。 BAM 管理ユーティリティは、基本的なインターセプター構成スキーマに対してインターセプター構成ファイルを検証し、ファイルが無効な場合はスキーマを展開しません。 ファイルが基本的なインターセプター構成スキーマに対する検証に合格すると、[!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)] スキーマや [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] スキーマなど、テクノロジ固有のスキーマに対して実行時に検証が行われ、エラーが発生した場合は傍受を行いません。 インターセプター構成ファイルを構築するときに、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のスキーマ検証を使用することで、これらのエラーを回避できます。  
  
> [!NOTE]
>  BAM インターセプタ構成 XSD ファイルのサンプルは、SDK ファイルと共にインストールされます。 このファイルは、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\BAM\InterceptorXSDs にあります。  
> 
> - CommonInterceptorConfiguration.xsd  
>   -   WcfInterceptorConfiguration.xsd  
>   -   WorkflowInterceptorConfiguration.xsd  
  
### <a name="to-obtain-a-copy-of-the-interceptor-schemas"></a>インターセプタ スキーマのコピーを取得するには  
  
1. メモ帳または任意のテキスト エディタを開きます。  
  
2. 移動し、[インターセプタ構成スキーマ](../core/interceptor-configuration-schema.md)トピック。  
  
3. 開いているテキスト エディターで新しいドキュメントに内容を貼り付けるし、名前を使用してテキスト ファイルとして保存します**CommonInterceptorConfiguration.xsd** (または、独自に選択のいずれか) をハード_ディスクにします。  
  
4. これらの手順を繰り返します、[!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)]スキーマと[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)]ファイル名を使用してスキーマ トピック**WorkflowInterceptorConfiguration.xsd**と**WcfInterceptorConfiguration.xsd**または名独自の次のように選択します。  
  
### <a name="to-use-intellisense-with-your-interceptor-configuration-file"></a>インターセプター構成ファイルで Intellisense を使用するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]を開きます。  
  
2. をクリックして**ファイル**、 をクリックして**新規**、 をクリックし、**ファイル**します。  
  
3. **新しいファイル**ダイアログ ボックスで、 **XML ファイル** をクリックし、**オープン**します。  
  
4. プロパティ ペインを表示、編集ウィンドウを右クリックし、をクリックして**プロパティ**します。  
  
5. プロパティ ペインで次のようにクリックします**スキーマ**、クリックして、省略記号 (**...**).  
  
6. **XML スキーマ**ダイアログ ボックスで、をクリックして**追加**クリックし、スキーマの場所に移動します**CommonInterceptorConfiguration.xsd**と**WcfInterceptorConfiguration.xsd**で作業している場合、[!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)]インターセプター構成ファイル、または**WorkflowInterceptorConfiguration.xsd**で作業している場合、 [!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)]インターセプター構成ファイル。  
  
   > [!NOTE]
   >  別の名前でファイルを保存した場合は、その名前を選択します。  
  
7. インターセプター構成ファイルを開くと [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] によりファイルが検証され、ファイルを作成および変更するときに Intellisense のヘルプが提供されます。  
  
## <a name="see-also"></a>参照  
 [Windows Workflow Foundation スキーマ](../core/windows-workflow-foundation-schema.md)   
 [Windows Communication Foundation スキーマ](../core/windows-communication-foundation-schema.md)