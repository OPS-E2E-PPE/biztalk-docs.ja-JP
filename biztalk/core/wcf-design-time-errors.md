---
title: WCF のデザイン時のエラー |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1327906a-6524-4937-830c-844d5fc81dc6
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 945093f62c9d0d45fd359dbfabe8a0e495850f6d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288786"
---
# <a name="wcf-design-time--errors"></a><span data-ttu-id="eba5c-102">WCF 設計時エラー</span><span class="sxs-lookup"><span data-stu-id="eba5c-102">WCF Design-Time  Errors</span></span>
<span data-ttu-id="eba5c-103">ここでは、WCF の設計時の構成エラーを診断および解決するための詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="eba5c-103">This section contains detailed information for diagnosing and resolving WCF design-time configuration errors.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eba5c-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="eba5c-104">In This Section</span></span>  
  
-   [<span data-ttu-id="eba5c-105">アクション エラー</span><span class="sxs-lookup"><span data-stu-id="eba5c-105">Action Errors</span></span>](../core/action-errors.md)  
  
-   [<span data-ttu-id="eba5c-106">アドレス エラー</span><span class="sxs-lookup"><span data-stu-id="eba5c-106">Address Errors</span></span>](../core/address-errors.md)  
  
-   [<span data-ttu-id="eba5c-107">アプリケーション エラー</span><span class="sxs-lookup"><span data-stu-id="eba5c-107">Application Errors</span></span>](../core/application-errors.md)  
  
-   [<span data-ttu-id="eba5c-108">アセンブリ エラー</span><span class="sxs-lookup"><span data-stu-id="eba5c-108">Assembly Errors</span></span>](../core/assembly-errors.md)  
  
-   [<span data-ttu-id="eba5c-109">バインド エラー</span><span class="sxs-lookup"><span data-stu-id="eba5c-109">Binding Errors</span></span>](../core/binding-errors.md)  
  
-   [<span data-ttu-id="eba5c-110">証明書のエラー</span><span class="sxs-lookup"><span data-stu-id="eba5c-110">Certificate Errors</span></span>](../core/certificate-errors.md)  
  
-   [<span data-ttu-id="eba5c-111">通信方式エラー</span><span class="sxs-lookup"><span data-stu-id="eba5c-111">Communication Pattern Errors</span></span>](../core/communication-pattern-errors.md)  
  
-   [<span data-ttu-id="eba5c-112">エラーのエラー処理</span><span class="sxs-lookup"><span data-stu-id="eba5c-112">Error Handling Errors</span></span>](../core/error-handling-errors.md)  
  
-   [<span data-ttu-id="eba5c-113">Id エラー</span><span class="sxs-lookup"><span data-stu-id="eba5c-113">Identity Errors</span></span>](../core/identity-errors.md)  
  
-   [<span data-ttu-id="eba5c-114">インポートおよびエクスポート エラー</span><span class="sxs-lookup"><span data-stu-id="eba5c-114">Import and Export Errors</span></span>](../core/import-and-export-errors.md)  
  
-   [<span data-ttu-id="eba5c-115">メタデータ エラー</span><span class="sxs-lookup"><span data-stu-id="eba5c-115">Metadata Errors</span></span>](../core/metadata-errors.md)  
  
-   [<span data-ttu-id="eba5c-116">名前のエラー</span><span class="sxs-lookup"><span data-stu-id="eba5c-116">Name Errors</span></span>](../core/name-errors.md)  
  
-   [<span data-ttu-id="eba5c-117">ポート構成エラー</span><span class="sxs-lookup"><span data-stu-id="eba5c-117">Port Configuration Errors</span></span>](../core/port-configuration-errors.md)  
  
-   [<span data-ttu-id="eba5c-118">プロパティ エラー</span><span class="sxs-lookup"><span data-stu-id="eba5c-118">Properties Errors</span></span>](../core/properties-errors.md)  
  
-   [<span data-ttu-id="eba5c-119">受信エラー</span><span class="sxs-lookup"><span data-stu-id="eba5c-119">Receive Errors</span></span>](../core/receive-errors.md)  
  
-   [<span data-ttu-id="eba5c-120">レジストリ エラー</span><span class="sxs-lookup"><span data-stu-id="eba5c-120">Registry Errors</span></span>](../core/registry-errors.md)  
  
-   [<span data-ttu-id="eba5c-121">スキーム エラー</span><span class="sxs-lookup"><span data-stu-id="eba5c-121">Scheme Errors</span></span>](../core/scheme-errors.md)  
  
-   [<span data-ttu-id="eba5c-122">エラーを送信します。</span><span class="sxs-lookup"><span data-stu-id="eba5c-122">Send Errors</span></span>](../core/send-errors.md)  
  
-   [<span data-ttu-id="eba5c-123">テンプレート エラー</span><span class="sxs-lookup"><span data-stu-id="eba5c-123">Template Errors</span></span>](../core/template-errors.md)  
  
-   [<span data-ttu-id="eba5c-124">タイムアウト エラー</span><span class="sxs-lookup"><span data-stu-id="eba5c-124">Timeout Errors</span></span>](../core/timeout-errors.md)