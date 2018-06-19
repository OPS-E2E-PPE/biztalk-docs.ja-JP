---
title: BAM WCF インターセプタ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2510008-4c89-436d-afd0-a98d9f803221
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 845348621f6bfcf6dbb41f286a320c5a6953ff39
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230570"
---
# <a name="bam-wcf-interceptor"></a><span data-ttu-id="09ba2-102">BAM WCF インターセプタ</span><span class="sxs-lookup"><span data-stu-id="09ba2-102">BAM WCF Interceptor</span></span>
<span data-ttu-id="09ba2-103">BAM WCF インターセプタは、WCF サービス内のデータの追跡を包括的にサポートします。</span><span class="sxs-lookup"><span data-stu-id="09ba2-103">The BAM WCF interceptor provides comprehensive support for tracking data within your WCF services.</span></span>  
  
 <span data-ttu-id="09ba2-104">BAM WCF インターセプタを使用すると、次の作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="09ba2-104">You can use the BAM WCF interceptor to:</span></span>  
  
-   <span data-ttu-id="09ba2-105">WCF アプリケーションを再コンパイルしなくても、ワークフロー アプリケーション データを BAM に透過的に配信します。</span><span class="sxs-lookup"><span data-stu-id="09ba2-105">Transparently deliver workflow application data to BAM without having to recompile your WCF application.</span></span>  
  
-   <span data-ttu-id="09ba2-106">WCF サービス呼び出し内のパラメータとメッセージの両方の情報を追跡します。</span><span class="sxs-lookup"><span data-stu-id="09ba2-106">Track information from both parameters and messages in WCF service calls.</span></span>  
  
-   <span data-ttu-id="09ba2-107">WCF サービス呼び出し内のメッセージの情報を追跡します。</span><span class="sxs-lookup"><span data-stu-id="09ba2-107">Track information from messages in WCF service calls.</span></span>  
  
-   <span data-ttu-id="09ba2-108">クライアントから流れてくるトランザクション、または実行されたサービス呼び出しに使用するために WCF ランタイムによって内部で開始されるトランザクションに参加します。</span><span class="sxs-lookup"><span data-stu-id="09ba2-108">Participate in transactions flowed from the client or initiated internally by the WCF runtime for transacted service calls.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="09ba2-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="09ba2-109">In This Section</span></span>  
  
-   [<span data-ttu-id="09ba2-110">傍受のための Windows Communication Foundation アプリケーションを構成する方法</span><span class="sxs-lookup"><span data-stu-id="09ba2-110">How to Configure a Windows Communication Foundation Application for Interception</span></span>](../core/configure-a-windows-communication-foundation-application-for-interception.md)  
  
-   [<span data-ttu-id="09ba2-111">Windows Communication Foundation スキーマ</span><span class="sxs-lookup"><span data-stu-id="09ba2-111">Windows Communication Foundation Schema</span></span>](../core/windows-communication-foundation-schema.md)  
  
-   [<span data-ttu-id="09ba2-112">Windows Communication Foundation での操作</span><span class="sxs-lookup"><span data-stu-id="09ba2-112">Operations in Windows Communication Foundation</span></span>](../core/operations-in-windows-communication-foundation.md)