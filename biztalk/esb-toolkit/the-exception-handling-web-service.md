---
title: "例外処理の Web サービス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dfe6ebdf-9b92-40c7-93fb-afd6c5f68aaa
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb8d8f3439e3b99d118e2932d0a158113ec51be2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-exception-handling-web-service"></a><span data-ttu-id="380df-102">例外処理の Web サービス</span><span class="sxs-lookup"><span data-stu-id="380df-102">The Exception Handling Web Service</span></span>
<span data-ttu-id="380df-103">例外処理 Web サービスは、エラー メッセージを受け入れるし、ESB 例外ポータルに公開します。</span><span class="sxs-lookup"><span data-stu-id="380df-103">The Exception Handling Web service accepts a fault message and publishes it to the ESB Exception Portal.</span></span> <span data-ttu-id="380df-104">クライアント アプリケーションでは、例外メッセージを作成でき、その例外の型またはジェネリック ハンドラー用に構成されたハンドラーが例外を処理できる、ESB に送信することができます。</span><span class="sxs-lookup"><span data-stu-id="380df-104">A client application can create exception messages and submit them to the ESB, where any handler configured for that exception type, or a generic handler, can process the exception.</span></span> <span data-ttu-id="380df-105">このサービスの主要な利点は、ESB 例外処理機構に参加する、ESB アプリケーションの外部エンティティできます。</span><span class="sxs-lookup"><span data-stu-id="380df-105">The major benefit of this service is that it allows entities outside an ESB application to participate in the ESB exception handling mechanism.</span></span>  
  
 <span data-ttu-id="380df-106">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このサービスの 2 つのバージョンが含まれています: ASP.NET (ASMX) バージョンと Windows Communication Foundation (WCF) バージョン。</span><span class="sxs-lookup"><span data-stu-id="380df-106">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] contains two versions of this service: an ASP.NET (ASMX) version and a Windows Communication Foundation (WCF) version.</span></span> <span data-ttu-id="380df-107">サービス名は**ESB です。ExceptionHandlingServices**と**ESB です。ExceptionHandlingServices.WCF**、それぞれ、およびサービスが 1 つのメソッドを公開します。</span><span class="sxs-lookup"><span data-stu-id="380df-107">The service names are **ESB.ExceptionHandlingServices** and **ESB.ExceptionHandlingServices.WCF**, respectively, and the services expose a single method:</span></span>  
  
-   <span data-ttu-id="380df-108">**SubmitFault**です。</span><span class="sxs-lookup"><span data-stu-id="380df-108">**SubmitFault**.</span></span> <span data-ttu-id="380df-109">このメソッドは、のインスタンスを受け取り、 **FaultMessage**クラス、戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="380df-109">This method takes an instance of the **FaultMessage** class and has no return value.</span></span>  
  
 <span data-ttu-id="380df-110">例外処理機構の動作方法に関する情報を参照してください。 [ESB 例外管理を使用して](../esb-toolkit/using-esb-exception-management.md)です。</span><span class="sxs-lookup"><span data-stu-id="380df-110">For information about the way the exception handling mechanism works, see [Using ESB Exception Management](../esb-toolkit/using-esb-exception-management.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="380df-111">既定では、例外処理の Web サービスは (SSL) クライアントによってアクセスされたときに要求するように構成されていません。</span><span class="sxs-lookup"><span data-stu-id="380df-111">By default, the Exception Handling Web services are not configured to require Secure Sockets Layer (SSL) when accessed by clients.</span></span> <span data-ttu-id="380df-112">クライアント アクセス用の SSL が要求されるようにサービスを構成し、インターネット インフォメーション サービス (IIS) Web サービスのホスト コンピューターとをホストするサーバー間の接続を保護する必要があります、 **ESBExceptions**データベースネットワーク レベルの IPSec および適切なファイル レベルのアクセス制御リスト (ACL) のアクセス許可を使用します。</span><span class="sxs-lookup"><span data-stu-id="380df-112">You should configure the service so that it requires SSL for client access and protect the connection between the Internet Information Services (IIS) Web service host computer and the server that hosts the **ESBExceptions** database using network-level IPSec and appropriate file-level access control list (ACL) permissions.</span></span>