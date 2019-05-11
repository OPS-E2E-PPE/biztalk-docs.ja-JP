---
title: BizTalk Server アダプターのトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 428b127f-df1e-4c41-9cc8-486519f15fa1
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 900e4bb481f2fd894c9ea186e57b516059b5052a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401875"
---
# <a name="troubleshooting-biztalk-server-adapters"></a><span data-ttu-id="b180c-102">BizTalk Server アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b180c-102">Troubleshooting BizTalk Server Adapters</span></span>
<span data-ttu-id="b180c-103">このトピックでは、BizTalk 統合アダプターで発生する可能性がある問題を特定および解決するために使用できる、一般的なトラブルシューティング手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="b180c-103">This topic describes common trouble shooting steps that can be used to identify and resolve problems that may be occurring in the BizTalk Integrated adapters.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b180c-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b180c-104">In This Section</span></span>  
  
-   [<span data-ttu-id="b180c-105">ファイル アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b180c-105">Troubleshooting the File Adapter</span></span>](../core/troubleshooting-the-file-adapter.md)  
  
-   [<span data-ttu-id="b180c-106">FTP アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b180c-106">Troubleshooting the FTP Adapter</span></span>](../core/troubleshooting-the-ftp-adapter.md)  
  
-   [<span data-ttu-id="b180c-107">HTTP アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b180c-107">Troubleshooting the HTTP Adapter</span></span>](../core/troubleshooting-the-http-adapter.md)  
  
-   [<span data-ttu-id="b180c-108">MQSeries アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b180c-108">Troubleshooting the MQSeries Adapter</span></span>](../core/troubleshooting-the-mqseries-adapter.md)  
  
-   [<span data-ttu-id="b180c-109">MSMQ アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b180c-109">Troubleshooting the MSMQ Adapter</span></span>](../core/troubleshooting-the-msmq-adapter.md)  
  
-   [<span data-ttu-id="b180c-110">POP3 アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b180c-110">Troubleshooting the POP3 Adapter</span></span>](../core/troubleshooting-the-pop3-adapter.md)  
  
-   [<span data-ttu-id="b180c-111">SMTP アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b180c-111">Troubleshooting the SMTP Adapter</span></span>](../core/troubleshooting-the-smtp-adapter.md)  
  
-   [<span data-ttu-id="b180c-112">SOAP アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b180c-112">Troubleshooting the SOAP Adapter</span></span>](../core/troubleshooting-the-soap-adapter.md)  
  
-   [<span data-ttu-id="b180c-113">Windows SharePoint Services アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b180c-113">Troubleshooting the Windows SharePoint Services Adapter</span></span>](../core/troubleshooting-the-windows-sharepoint-services-adapter.md)  
  
-   [<span data-ttu-id="b180c-114">WCF アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b180c-114">Troubleshooting the WCF Adapters</span></span>](../core/troubleshooting-the-wcf-adapters.md)  
  
-   [<span data-ttu-id="b180c-115">BizTalk アダプターのトレースの使用</span><span class="sxs-lookup"><span data-stu-id="b180c-115">Using BizTalk Adapter Tracing</span></span>](../core/using-biztalk-adapter-tracing.md)  
  
-   [<span data-ttu-id="b180c-116">BizTalk アダプターにおける IPv6 アドレス指定の使用</span><span class="sxs-lookup"><span data-stu-id="b180c-116">Using IPv6 Addressing with BizTalk Adapters</span></span>](../core/using-ipv6-addressing-with-biztalk-adapters.md)