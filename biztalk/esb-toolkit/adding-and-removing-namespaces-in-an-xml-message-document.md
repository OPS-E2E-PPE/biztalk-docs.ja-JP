---
title: ドキュメントをメッセージを追加して、XML で名前空間を削除する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dbf2f209-13b9-42e0-b0f2-b53ec705e84b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3bb3b28504f92164aca1f66902546f1e04a2290
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289442"
---
# <a name="adding-and-removing-namespaces-in-an-xml-message-document"></a><span data-ttu-id="325c3-102">追加して、XML メッセージ ドキュメント内の名前空間を削除します。</span><span class="sxs-lookup"><span data-stu-id="325c3-102">Adding and Removing Namespaces in an XML Message Document</span></span>
<span data-ttu-id="325c3-103">このユース ケースでは、Namespace コンポーネントがで提供される、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]名前空間の追加または削除の名前空間、ドキュメントおよびメッセージ、図 1 に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="325c3-103">In this use case, the Namespace component provided with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] adds namespaces to, or removes namespaces from, documents and messages, as illustrated in Figure 1.</span></span> <span data-ttu-id="325c3-104">これは、名前空間の競合またはドキュメントが既定の名前空間を使用するときに発生したエラーを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="325c3-104">This prevents namespace clashes or errors arising when documents use default namespaces.</span></span>  
  
 <span data-ttu-id="325c3-105">![削除する名前空間を追加する](../esb-toolkit/media/ch3-addingremovingnamespaces.gif "Ch3 AddingRemovingNamespaces")</span><span class="sxs-lookup"><span data-stu-id="325c3-105">![Adding Removing Namespaces](../esb-toolkit/media/ch3-addingremovingnamespaces.gif "Ch3-AddingRemovingNamespaces")</span></span>  
  
 <span data-ttu-id="325c3-106">**図 1**</span><span class="sxs-lookup"><span data-stu-id="325c3-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="325c3-107">**追加して、XML ドキュメントおよびメッセージの名前空間を削除します。**</span><span class="sxs-lookup"><span data-stu-id="325c3-107">**Adding and removing XML document and message namespaces**</span></span>  
  
 <span data-ttu-id="325c3-108">含まれている Namespace コンポーネント サンプル、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示しています。</span><span class="sxs-lookup"><span data-stu-id="325c3-108">The Namespace Component sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="325c3-109">挿入し、送信および受信プロセスの一部として、ドキュメント内の名前空間を削除するコンポーネントを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="325c3-109">It shows how to use the component to inject and remove namespaces in a document as part of the send and the receive process.</span></span>  
  
 <span data-ttu-id="325c3-110">詳細については、次を参照してください。[をインストールすると、Namespace コンポーネント サンプルを実行している](../esb-toolkit/installing-and-running-the-namespace-component-sample.md)です。</span><span class="sxs-lookup"><span data-stu-id="325c3-110">For more information, see [Installing and Running the Namespace Component Sample](../esb-toolkit/installing-and-running-the-namespace-component-sample.md).</span></span>