---
title: "アダプターを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: adapters
ms.assetid: afdfa70e-5929-4746-99b4-e76274aa5c88
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18ffc3c198cbd6fc26290908dfcc3a90b2c8a62a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-adapters"></a><span data-ttu-id="7fa8a-102">アダプターの使用</span><span class="sxs-lookup"><span data-stu-id="7fa8a-102">Using Adapters</span></span>
<span data-ttu-id="7fa8a-103">このセクションでは、アダプターの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="7fa8a-103">This section contains comprehensive information about adapters.</span></span> <span data-ttu-id="7fa8a-104">ここでは、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] におけるアダプタの使用方法と、各アダプタのアダプタ ハンドラ、送信ポート、および受信場所の構成方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7fa8a-104">It describes how adapters are used in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and how to configure adapter handlers, send ports, and receive locations for each adapter.</span></span> <span data-ttu-id="7fa8a-105">また、ネイティブ アダプターについて理解を深め、BizTalk ソリューションで使用するために役立つバッチ処理のサポート情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="7fa8a-105">It provides batching support information to help you understand and use the native adapters in your BizTalk solution.</span></span>  
  
 <span data-ttu-id="7fa8a-106">アダプターのプロパティ ページのキーボード ショートカットの使用方法の詳細については、次を参照してください。[アダプター プロパティ ページのキーボード ショートカット](../core/adapter-property-page-keyboard-shortcuts.md)です。</span><span class="sxs-lookup"><span data-stu-id="7fa8a-106">For information about using the keyboard shortcuts for the adapter property pages, see [Adapter Property Page Keyboard Shortcuts](../core/adapter-property-page-keyboard-shortcuts.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7fa8a-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7fa8a-107">In This Section</span></span>  
  
-   [<span data-ttu-id="7fa8a-108">BizTalk Server のアダプター</span><span class="sxs-lookup"><span data-stu-id="7fa8a-108">Adapters in BizTalk Server</span></span>](../core/adapters-in-biztalk-server.md)  
  
-   [<span data-ttu-id="7fa8a-109">動的送信ポート ハンドラーは構成可能です。</span><span class="sxs-lookup"><span data-stu-id="7fa8a-109">Dynamic Send Port Handler is Configurable</span></span>](../core/dynamic-send-port-handler-is-configurable.md)  
  
-   [<span data-ttu-id="7fa8a-110">アダプターのセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="7fa8a-110">Security Considerations for Adapters</span></span>](../core/security-considerations-for-adapters.md)  
  
-   [<span data-ttu-id="7fa8a-111">Sb-messaging アダプター</span><span class="sxs-lookup"><span data-stu-id="7fa8a-111">SB-Messaging adapter</span></span>](../core/sb-messaging-adapter.md)  
  
-   [<span data-ttu-id="7fa8a-112">ファイル アダプター</span><span class="sxs-lookup"><span data-stu-id="7fa8a-112">File adapter</span></span>](../core/file-adapter.md)  
  
-   [<span data-ttu-id="7fa8a-113">FTP アダプター</span><span class="sxs-lookup"><span data-stu-id="7fa8a-113">FTP adapter</span></span>](../core/ftp-adapter.md)  

- [<span data-ttu-id="7fa8a-114">ロジック アプリのアダプター</span><span class="sxs-lookup"><span data-stu-id="7fa8a-114">Logic App adapter</span></span>](../core/logic-app-adapter.md)
  
-   [<span data-ttu-id="7fa8a-115">SFTP アダプター</span><span class="sxs-lookup"><span data-stu-id="7fa8a-115">SFTP adapter</span></span>](../core/sftp-adapter.md)  
  
-   [<span data-ttu-id="7fa8a-116">HTTP アダプター</span><span class="sxs-lookup"><span data-stu-id="7fa8a-116">HTTP adapter</span></span>](../core/http-adapter.md)  
  
-   [<span data-ttu-id="7fa8a-117">JD Edwards EnterpriseOne アダプター</span><span class="sxs-lookup"><span data-stu-id="7fa8a-117">JD Edwards EnterpriseOne adapter</span></span>](../core/jd-edwards-enterpriseone-adapter.md) 
  
-   [<span data-ttu-id="7fa8a-118">JD Edwards OneWorld アダプター</span><span class="sxs-lookup"><span data-stu-id="7fa8a-118">JD Edwards OneWorld adapter</span></span>](../core/jd-edwards-oneworld-adapter.md)  
  
-   [<span data-ttu-id="7fa8a-119">Oracle E-business Suite ODBC アダプタ</span><span class="sxs-lookup"><span data-stu-id="7fa8a-119">Oracle E-Business Suite ODBC adapter</span></span>](../core/oracle-e-business-suite-odbc-adapter.md)  
  
-   [<span data-ttu-id="7fa8a-120">Oracle Database ODBC アダプタ</span><span class="sxs-lookup"><span data-stu-id="7fa8a-120">Oracle Database ODBC adapter</span></span>](../core/oracle-database-odbc-adapter.md)  
  
-   [<span data-ttu-id="7fa8a-121">PeopleSoft Enterprise アダプター</span><span class="sxs-lookup"><span data-stu-id="7fa8a-121">PeopleSoft Enterprise adapter</span></span>](../core/peoplesoft-enterprise-adapter.md)  
  
-   [<span data-ttu-id="7fa8a-122">Siebel eBusiness Applications アダプタ</span><span class="sxs-lookup"><span data-stu-id="7fa8a-122">Siebel eBusiness Applications adapter</span></span>](../core/siebel-ebusiness-applications-adapter.md)  
  
-   [<span data-ttu-id="7fa8a-123">TIBCO Enterprise Message Service アダプタ</span><span class="sxs-lookup"><span data-stu-id="7fa8a-123">TIBCO Enterprise Message Service adapter</span></span>](../core/tibco-enterprise-message-service-adapter.md)  
  
-   [<span data-ttu-id="7fa8a-124">TIBCO Rendezvous アダプター</span><span class="sxs-lookup"><span data-stu-id="7fa8a-124">TIBCO Rendezvous adapter</span></span>](../core/tibco-rendezvous-adapter.md)  
  
-   [<span data-ttu-id="7fa8a-125">MQSeries アダプター</span><span class="sxs-lookup"><span data-stu-id="7fa8a-125">MQSeries adapter</span></span>](../core/mqseries-adapter.md)  
  
-   [<span data-ttu-id="7fa8a-126">MSMQ アダプター</span><span class="sxs-lookup"><span data-stu-id="7fa8a-126">MSMQ adapter</span></span>](../core/msmq-adapter.md)  
  
-   [<span data-ttu-id="7fa8a-127">POP3 アダプター</span><span class="sxs-lookup"><span data-stu-id="7fa8a-127">POP3 adapter</span></span>](../core/pop3-adapter.md)  
  
-   [<span data-ttu-id="7fa8a-128">SAP アダプター</span><span class="sxs-lookup"><span data-stu-id="7fa8a-128">SAP adapter</span></span>](../core/sap-adapter.md)  
  
-   [<span data-ttu-id="7fa8a-129">SMTP アダプター</span><span class="sxs-lookup"><span data-stu-id="7fa8a-129">SMTP adapter</span></span>](../core/smtp-adapter.md)  
  
-   [<span data-ttu-id="7fa8a-130">SOAP アダプター</span><span class="sxs-lookup"><span data-stu-id="7fa8a-130">SOAP adapter</span></span>](../core/soap-adapter.md)  
  
-   [<span data-ttu-id="7fa8a-131">SQL アダプター</span><span class="sxs-lookup"><span data-stu-id="7fa8a-131">SQL adapter</span></span>](../core/sql-adapter.md)  
  
-   [<span data-ttu-id="7fa8a-132">Windows SharePoint Services アダプター</span><span class="sxs-lookup"><span data-stu-id="7fa8a-132">Windows SharePoint Services adapter</span></span>](../core/windows-sharepoint-services-adapter.md)  
  
-   [<span data-ttu-id="7fa8a-133">WCF アダプタ</span><span class="sxs-lookup"><span data-stu-id="7fa8a-133">WCF adapters</span></span>](../core/wcf-adapters.md)  
  
-   [<span data-ttu-id="7fa8a-134">作成して、アダプター ハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="7fa8a-134">Creating and Deleting Adapter Handlers</span></span>](../core/creating-and-deleting-adapter-handlers.md)  
  
-   [<span data-ttu-id="7fa8a-135">アダプターのパフォーマンスに影響する構成パラメーター</span><span class="sxs-lookup"><span data-stu-id="7fa8a-135">Configuration Parameters that Affect Adapter Performance</span></span>](../core/configuration-parameters-that-affect-adapter-performance.md)  
  
-   [<span data-ttu-id="7fa8a-136">BizTalk Server アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="7fa8a-136">Troubleshooting BizTalk Server Adapters</span></span>](../core/troubleshooting-biztalk-server-adapters.md)  
  
-   [<span data-ttu-id="7fa8a-137">アダプターの追加情報</span><span class="sxs-lookup"><span data-stu-id="7fa8a-137">Additional Adapter Information</span></span>](../core/additional-adapter-information.md)