---
title: Siebel アダプターを使用して BizTalk アプリケーションの開発 |Microsoft Docs
ms.custom: ''
ms.date: 08/02/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk applications, developing
- developing, BizTalk applications
- CBR
- Content-Based Routing
ms.assetid: 1a2a9765-305c-44b2-aed7-5437725e4c19
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9302dca6a86cbc149a0fd5aa23acc844ff803ff8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371717"
---
# <a name="develop-biztalk-applications-using-the-siebel-adapter"></a><span data-ttu-id="40701-102">Siebel アダプターを使用して BizTalk アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="40701-102">Develop BizTalk applications using the Siebel adapter</span></span>

## <a name="overview"></a><span data-ttu-id="40701-103">概要</span><span class="sxs-lookup"><span data-stu-id="40701-103">Overview</span></span>
<span data-ttu-id="40701-104">BizTalk アプリケーションを開発する場合で BizTalk プロジェクトを作成する必要があります[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用して、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] XML スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="40701-104">Developing BizTalk applications involves creating a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to generate XML schema.</span></span> <span data-ttu-id="40701-105">スキーマが生成されると、コンテンツ ベースのルーティング (CBR) を使用するか、または、生成されたスキーマに準拠するメッセージを送受信する BizTalk オーケストレーションを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="40701-105">Once you have generated the schema, you can either use Content-Based Routing (CBR) or create BizTalk orchestrations to send and receive messages that conform to the generated schema.</span></span>  
  
 <span data-ttu-id="40701-106">CBR は、場所、Siebel システムに送信されるメッセージには、処理を要する処理は不要のシナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="40701-106">CBR can be used in scenarios where the messages being sent to a Siebel system do not require any intensive processing.</span></span> <span data-ttu-id="40701-107">たとえば、受信ポートが特定の型だけのメッセージを受信することがわかっている場合は、送信ポートにフィルター式に一致するメッセージをルーティングする送信ポートにフィルターを追加できます。</span><span class="sxs-lookup"><span data-stu-id="40701-107">For example, if you know that the receive port will be receiving messages only of a certain type, you can add a filter to the send port to route the messages matching the filter expression to the send port.</span></span>  
  
 <span data-ttu-id="40701-108">、BizTalk オーケストレーションの送信を作成およびとの間でメッセージを送受信する受信ポート、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、さらに、メッセージを送信する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="40701-108">In BizTalk orchestrations, you create send and receive ports to send and receive messages to and from the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], which in turn sends the messages to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="40701-109">このセクションを使用して Siebel システムの操作を実行する BizTalk オーケストレーションを使用する方法について説明します、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="40701-109">This section provides information about using BizTalk orchestrations to perform operations on a Siebel system using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="40701-110">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]順番に使用して、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)] WCF バインドと対話することができます。</span><span class="sxs-lookup"><span data-stu-id="40701-110">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] in turn uses the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)] that can interact with a WCF binding.</span></span>  

## <a name="before-you-begin"></a><span data-ttu-id="40701-111">アンインストールの準備</span><span class="sxs-lookup"><span data-stu-id="40701-111">Before you begin</span></span>  

* <span data-ttu-id="40701-112">使用する、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、常に設定されて、 **EnableBizTalkCompatibilityMode**プロパティをバインド**True**します。</span><span class="sxs-lookup"><span data-stu-id="40701-112">To use the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], always set the **EnableBizTalkCompatibilityMode** binding property to **True**.</span></span> <span data-ttu-id="40701-113">手順については、次を参照してください。 [for Siebel のバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-siebel/configure-the-binding-properties-for-siebel.md)します。</span><span class="sxs-lookup"><span data-stu-id="40701-113">For the steps, see [Configure the binding properties for Siebel](../../adapters-and-accelerators/adapter-siebel/configure-the-binding-properties-for-siebel.md).</span></span>
  
* <span data-ttu-id="40701-114">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]付属[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]は、BizTalk Server 管理コンソールに自動的に表示されません。</span><span class="sxs-lookup"><span data-stu-id="40701-114">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] shipped with [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is not automatically listed in the BizTalk Server Administration console.</span></span> <span data-ttu-id="40701-115">これは、ため、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] WCF カスタム バインドします。</span><span class="sxs-lookup"><span data-stu-id="40701-115">This is because the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is a WCF custom binding.</span></span> 

* <span data-ttu-id="40701-116">メタデータを生成するには、使用、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="40701-116">To generate metadata, use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].</span></span> <span data-ttu-id="40701-117">使用しないでください、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="40701-117">Do not use the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="40701-118">使用方法について、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を参照してください[Visual Studio で Siebel 操作のメタデータの取得](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)します。</span><span class="sxs-lookup"><span data-stu-id="40701-118">For instructions on using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], see [Get Metadata for Siebel Operations in Visual Studio](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md).</span></span>   

  
## <a name="see-also"></a><span data-ttu-id="40701-119">参照</span><span class="sxs-lookup"><span data-stu-id="40701-119">See Also</span></span>  
[<span data-ttu-id="40701-120">Siebel アプリケーションの開発</span><span class="sxs-lookup"><span data-stu-id="40701-120">Develop your Siebel applications</span></span>](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)