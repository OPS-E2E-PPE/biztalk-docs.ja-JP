---
title: WCF デザイン時エラー |Microsoft Docs
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
ms.openlocfilehash: ee67253478220a5fb018beb7ad27ae85eac7693e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399124"
---
# <a name="wcf-design-time--errors"></a><span data-ttu-id="46f38-102">WCF デザイン時エラー</span><span class="sxs-lookup"><span data-stu-id="46f38-102">WCF Design-Time  Errors</span></span>
<span data-ttu-id="46f38-103">ここでは、WCF の設計時の構成エラーを診断および解決するための詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="46f38-103">This section contains detailed information for diagnosing and resolving WCF design-time configuration errors.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="46f38-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="46f38-104">In This Section</span></span>  
  
-   [<span data-ttu-id="46f38-105">アクション エラー</span><span class="sxs-lookup"><span data-stu-id="46f38-105">Action Errors</span></span>](../core/action-errors.md)  
  
-   [<span data-ttu-id="46f38-106">アドレス エラー</span><span class="sxs-lookup"><span data-stu-id="46f38-106">Address Errors</span></span>](../core/address-errors.md)  
  
-   [<span data-ttu-id="46f38-107">アプリケーション エラー</span><span class="sxs-lookup"><span data-stu-id="46f38-107">Application Errors</span></span>](../core/application-errors.md)  
  
-   [<span data-ttu-id="46f38-108">アセンブリ エラー</span><span class="sxs-lookup"><span data-stu-id="46f38-108">Assembly Errors</span></span>](../core/assembly-errors.md)  
  
-   [<span data-ttu-id="46f38-109">バインド エラー</span><span class="sxs-lookup"><span data-stu-id="46f38-109">Binding Errors</span></span>](../core/binding-errors.md)  
  
-   [<span data-ttu-id="46f38-110">証明書エラー</span><span class="sxs-lookup"><span data-stu-id="46f38-110">Certificate Errors</span></span>](../core/certificate-errors.md)  
  
-   [<span data-ttu-id="46f38-111">通信方式エラー</span><span class="sxs-lookup"><span data-stu-id="46f38-111">Communication Pattern Errors</span></span>](../core/communication-pattern-errors.md)  
  
-   [<span data-ttu-id="46f38-112">エラー処理エラー</span><span class="sxs-lookup"><span data-stu-id="46f38-112">Error Handling Errors</span></span>](../core/error-handling-errors.md)  
  
-   [<span data-ttu-id="46f38-113">ID エラー</span><span class="sxs-lookup"><span data-stu-id="46f38-113">Identity Errors</span></span>](../core/identity-errors.md)  
  
-   [<span data-ttu-id="46f38-114">インポートおよびエクスポート エラー</span><span class="sxs-lookup"><span data-stu-id="46f38-114">Import and Export Errors</span></span>](../core/import-and-export-errors.md)  
  
-   [<span data-ttu-id="46f38-115">メタデータ エラー</span><span class="sxs-lookup"><span data-stu-id="46f38-115">Metadata Errors</span></span>](../core/metadata-errors.md)  
  
-   [<span data-ttu-id="46f38-116">名前エラー</span><span class="sxs-lookup"><span data-stu-id="46f38-116">Name Errors</span></span>](../core/name-errors.md)  
  
-   [<span data-ttu-id="46f38-117">ポート構成エラー</span><span class="sxs-lookup"><span data-stu-id="46f38-117">Port Configuration Errors</span></span>](../core/port-configuration-errors.md)  
  
-   [<span data-ttu-id="46f38-118">プロパティ エラー</span><span class="sxs-lookup"><span data-stu-id="46f38-118">Properties Errors</span></span>](../core/properties-errors.md)  
  
-   [<span data-ttu-id="46f38-119">受信エラー</span><span class="sxs-lookup"><span data-stu-id="46f38-119">Receive Errors</span></span>](../core/receive-errors.md)  
  
-   [<span data-ttu-id="46f38-120">レジストリ エラー</span><span class="sxs-lookup"><span data-stu-id="46f38-120">Registry Errors</span></span>](../core/registry-errors.md)  
  
-   [<span data-ttu-id="46f38-121">スキーム エラー</span><span class="sxs-lookup"><span data-stu-id="46f38-121">Scheme Errors</span></span>](../core/scheme-errors.md)  
  
-   [<span data-ttu-id="46f38-122">送信エラー</span><span class="sxs-lookup"><span data-stu-id="46f38-122">Send Errors</span></span>](../core/send-errors.md)  
  
-   [<span data-ttu-id="46f38-123">テンプレート エラー</span><span class="sxs-lookup"><span data-stu-id="46f38-123">Template Errors</span></span>](../core/template-errors.md)  
  
-   [<span data-ttu-id="46f38-124">タイムアウト エラー</span><span class="sxs-lookup"><span data-stu-id="46f38-124">Timeout Errors</span></span>](../core/timeout-errors.md)