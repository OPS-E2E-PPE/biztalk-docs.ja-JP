---
title: SAP アダプター クライアントの機能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- dynamic ports
- adapters, features
- XML data streaming
- performance counters
- adapters, support for dynamic ports in BizTalk Server
- adapters, support for message versioning
- adapters, support for XML data streaming
- adapters, support for performance counters
- adapters, support for configuring adapters using binding properties
ms.assetid: 9003c2c1-931d-405e-9a58-660032195af7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 832df9dfe3384a239ab4e4148229e9bc65f65e77
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373452"
---
# <a name="features-for-sap-adapter-clients"></a><span data-ttu-id="3c156-102">SAP アダプター クライアントの機能</span><span class="sxs-lookup"><span data-stu-id="3c156-102">Features for SAP adapter clients</span></span>
<span data-ttu-id="3c156-103">トピックで説明されている機能だけでなく[mySAP Business Suite の BizTalk アダプターのアーキテクチャの概要](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]アダプター クライアントに役立つ次の機能も提供します。</span><span class="sxs-lookup"><span data-stu-id="3c156-103">In addition to the features discussed throughout the topics of [Architecture overview of BizTalk Adapter for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md), the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] also provides the following features that are useful for adapter clients.</span></span>  
  
- <span data-ttu-id="3c156-104">**バインドのプロパティを使用してアダプターを構成するためのサポート**します。</span><span class="sxs-lookup"><span data-stu-id="3c156-104">**Support for configuring adapters using binding properties**.</span></span> <span data-ttu-id="3c156-105">アダプター クライアントを構成することができます、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]特定のバインド プロパティを指定しています。</span><span class="sxs-lookup"><span data-stu-id="3c156-105">Adapter clients can configure the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] by specifying certain binding properties.</span></span> <span data-ttu-id="3c156-106">クライアントが、アダプターの接続プール内の値を指定することによって接続の最大数を指定するアダプターを構成するなど、 **MaxConnectionsPerSystem**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="3c156-106">For example, clients can configure the adapter to specify the maximum number of connections in the adapter's connection pool by specifying a value for the **MaxConnectionsPerSystem** binding property.</span></span> <span data-ttu-id="3c156-107">詳細については、次を参照してください。 [mySAP Business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="3c156-107">For more information, see [Read about BizTalk Adapter for mySAP Business Suite Binding Properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
- <span data-ttu-id="3c156-108">**BizTalk Server で動的ポートのサポート**します。</span><span class="sxs-lookup"><span data-stu-id="3c156-108">**Support for dynamic ports in BizTalk Server**.</span></span> <span data-ttu-id="3c156-109">BizTalk から[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]からのメッセージの動的ルーティングできるようにする動的ポートをサポートしている[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージ コンテキスト プロパティに基づきます。</span><span class="sxs-lookup"><span data-stu-id="3c156-109">Through the BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports a dynamic port that enables dynamic routing of messages from [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] based on the message context properties.</span></span> <span data-ttu-id="3c156-110">詳細については、次を参照してください。[動的ポートを構成する](../../adapters-and-accelerators/adapter-sap/configure-dynamic-ports-in-the-sap-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="3c156-110">For more information, see [Configure dynamic ports](../../adapters-and-accelerators/adapter-sap/configure-dynamic-ports-in-the-sap-adapter.md).</span></span>
  
- <span data-ttu-id="3c156-111">**メッセージのバージョン管理のサポート**します。</span><span class="sxs-lookup"><span data-stu-id="3c156-111">**Support for message versioning**.</span></span> <span data-ttu-id="3c156-112">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]メッセージの今後のリリースでのさまざまなメッセージ スキーマのサポートを有効にバージョン管理をサポートしています、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3c156-112">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports message versioning to enable support for different message schemas in future releases of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="3c156-113">詳細については、次を参照してください。[メッセージ バージョン管理サポート](../../adapters-and-accelerators/adapter-sap/message-versioning-support1.md)します。</span><span class="sxs-lookup"><span data-stu-id="3c156-113">For more information, see [Message Versioning Support](../../adapters-and-accelerators/adapter-sap/message-versioning-support1.md).</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="3c156-114">この機能は、アダプターの以前のバージョンとの下位互換性を提供しません。</span><span class="sxs-lookup"><span data-stu-id="3c156-114">This feature does not provide backward compatibility with the earlier versions of the adapter.</span></span>  
  
- <span data-ttu-id="3c156-115">**パフォーマンス カウンターのサポート**します。</span><span class="sxs-lookup"><span data-stu-id="3c156-115">**Support for performance counters**.</span></span> <span data-ttu-id="3c156-116">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]アダプター クライアントで使用するための WCF ベースのパフォーマンス カウンターをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3c156-116">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports WCF-based performance counters for use by adapter clients.</span></span> <span data-ttu-id="3c156-117">パフォーマンス カウンターの詳細については、次を参照してください。 [SAP アダプターを使用したパフォーマンス カウンターを使用して](../../adapters-and-accelerators/adapter-sap/use-performance-counters-with-the-sap-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="3c156-117">For more information about performance counters, see [Use Performance Counters with the SAP adapter](../../adapters-and-accelerators/adapter-sap/use-performance-counters-with-the-sap-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c156-118">参照</span><span class="sxs-lookup"><span data-stu-id="3c156-118">See Also</span></span>  
 [<span data-ttu-id="3c156-119">BizTalk Adapter 用 mySAP Business Suite のアーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="3c156-119">Architecture overview of BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)