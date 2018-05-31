---
title: MapHelper クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c552c066-835f-4515-939f-dd465a7a5ed0
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de74610c40b37560abcbce040d80320525f0a21c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295114"
---
# <a name="the-maphelper-class"></a><span data-ttu-id="d0055-102">MapHelper クラス</span><span class="sxs-lookup"><span data-stu-id="d0055-102">The MapHelper Class</span></span>
<span data-ttu-id="d0055-103">使用して、 **MapHelper**変換 Web サービスを使用せずに直接変換を実行するクラス。</span><span class="sxs-lookup"><span data-stu-id="d0055-103">Use the **MapHelper** class to perform transformations directly without using the transformation Web service.</span></span>  
  
 <span data-ttu-id="d0055-104">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]インストーラーは、アセンブリを登録、 **Microsof.Practices.ESB.Transform.dll**で、 **MapHelper**グローバル アセンブリ キャッシュ内のクラスです。</span><span class="sxs-lookup"><span data-stu-id="d0055-104">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] installer installs and registers the assembly **Microsof.Practices.ESB.Transform.dll** with the **MapHelper** class in the global assembly cache.</span></span>  
  
 <span data-ttu-id="d0055-105">**MapHelper**クラスは、次の 2 つのパブリック メソッドを公開します。</span><span class="sxs-lookup"><span data-stu-id="d0055-105">The **MapHelper** class exposes two public methods:</span></span>  
  
-   <span data-ttu-id="d0055-106">**TransformMessage**です。</span><span class="sxs-lookup"><span data-stu-id="d0055-106">**TransformMessage**.</span></span> <span data-ttu-id="d0055-107">このメソッドは、変換するメッセージを含む文字列と BizTalk に展開されているマップの完全修飾名を含む文字列パラメーターとして受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d0055-107">This method takes as parameters a string that contains the message to transform and a string that contains the fully qualified name of a map deployed in BizTalk.</span></span> <span data-ttu-id="d0055-108">メソッドは、変換されたドキュメントを含む文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="d0055-108">The method returns a string containing the transformed document.</span></span>  
  
-   <span data-ttu-id="d0055-109">**TransformMessageStream**です。</span><span class="sxs-lookup"><span data-stu-id="d0055-109">**TransformMessageStream**.</span></span> <span data-ttu-id="d0055-110">このメソッドは、変換するメッセージを格納しているストリームと BizTalk に展開されているマップの完全修飾名を含む文字列パラメーターとして受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d0055-110">This method takes as parameters a stream that contains the message to transform and a string that contains the fully qualified name of a map deployed in BizTalk.</span></span> <span data-ttu-id="d0055-111">メソッドは、変換されたドキュメントを含む文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="d0055-111">The method returns a string that contains the transformed document.</span></span>