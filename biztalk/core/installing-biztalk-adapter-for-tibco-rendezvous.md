---
title: TIBCO Rendezvous アダプターのインストール、スキーマ、および制限事項 |Microsoft Docs
description: インストール、スキーマの生成、および BizTalk Server で TIBCO Rendezvous の BizTalk アダプターの制限事項
ms.custom: ''
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6404e7e-f671-4c57-a222-0bbe7cbc334f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f00e77a4eb2234265430f3cadc6a8384d768d16
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382080"
---
# <a name="install-schemas-and-limitations-of-the-tibco-rendezvous-adapter"></a><span data-ttu-id="46ea0-103">インストール、スキーマ、および、TIBCO Rendezvous アダプターの制限事項</span><span class="sxs-lookup"><span data-stu-id="46ea0-103">Install, schemas, and limitations of the TIBCO Rendezvous adapter</span></span>

## <a name="install-and-setup"></a><span data-ttu-id="46ea0-104">インストールとセットアップ</span><span class="sxs-lookup"><span data-stu-id="46ea0-104">Install and setup</span></span>

<span data-ttu-id="46ea0-105">[インストールし、構成のエンタープライズ アプリケーション アダプター](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md)エンタープライズ アダプターをインストールする手順を含み、キーの情報を知ると、アダプターをインストールする前に、アダプターをインストールした後も含まれます。</span><span class="sxs-lookup"><span data-stu-id="46ea0-105">[Install and configure the adapters for enterprise applications](../adapters-and-accelerators/install-configure-biztalk-adapters-enterprise-applications.md) includes the steps to install the enterprise adapters, and also includes key information to know before you install the adapter, and after you install the adapter.</span></span> 

## <a name="generate-schemas"></a><span data-ttu-id="46ea0-106">スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="46ea0-106">Generate schemas</span></span>
<span data-ttu-id="46ea0-107">TIBCO Rendezvous システムでは、メッセージの種類のリポジトリは含まれません。</span><span class="sxs-lookup"><span data-stu-id="46ea0-107">A TIBCO Rendezvous system does not include a message types repository.</span></span> <span data-ttu-id="46ea0-108">すべてのメッセージの構築と解析が、Rendezvous アプリケーション レベルで埋め込まれています。</span><span class="sxs-lookup"><span data-stu-id="46ea0-108">All the message construction and parsing is buried at the Rendezvous application level.</span></span> <span data-ttu-id="46ea0-109">この制限により、アダプターは、スキーマ生成機能を提供できません。</span><span class="sxs-lookup"><span data-stu-id="46ea0-109">Because of this limitation, adapter cannot provide schema-generation capabilities.</span></span>  
  
<span data-ttu-id="46ea0-110">スキーマを記述して、使用する必要があります**既存項目の追加**Visual Studio でオーケストレーション用にインポートします。</span><span class="sxs-lookup"><span data-stu-id="46ea0-110">You must write a schema, and use **Add Existing Item** in Visual Studio to import it for use in orchestrations.</span></span> <span data-ttu-id="46ea0-111">スキーマは、BizTalk Server 開発ツールと Visual Studio での統合のために非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="46ea0-111">Schemas are very important for BizTalk Server development tools and for integration in Visual Studio.</span></span> <span data-ttu-id="46ea0-112">BizTalk Server の開発者は、完全なスキーマ、必要最低限のスキーマまたはとの間のどこかのバージョンの提供を選択できます。</span><span class="sxs-lookup"><span data-stu-id="46ea0-112">BizTalk Server developers can choose to provide a complete schema, a minimalist schema, or a version somewhere in between.</span></span>  

## <a name="limitations"></a><span data-ttu-id="46ea0-113">制限事項</span><span class="sxs-lookup"><span data-stu-id="46ea0-113">Limitations</span></span>

- <span data-ttu-id="46ea0-114">フィールドの名前の一意性は保証されません。</span><span class="sxs-lookup"><span data-stu-id="46ea0-114">Field name uniqueness is not guaranteed.</span></span> <span data-ttu-id="46ea0-115">TIBCO Rendezvous メッセージに 2 つの同じフィールド名がある場合、生成される XML は無効になります。</span><span class="sxs-lookup"><span data-stu-id="46ea0-115">If a TIBCO Rendezvous message contains two field names that are the same, the resulting XML is not valid.</span></span>  
  
- <span data-ttu-id="46ea0-116">フィールドを並べ替えることはできません。</span><span class="sxs-lookup"><span data-stu-id="46ea0-116">Field ordering/sorting is not provided.</span></span>  
  
- <span data-ttu-id="46ea0-117">TIBCO Rendezvous のドキュメントによると、サブジェクト名には印刷できない文字を使用できないことになっていますが、そのような文字を使用することはできます。</span><span class="sxs-lookup"><span data-stu-id="46ea0-117">According to TIBCO Rendezvous documentation, non-printable characters are not used in subject names; however, it is still possible that such characters are used.</span></span> <span data-ttu-id="46ea0-118">BizTalk Adapter for TIBCO Rendezvous では印刷できない文字が入ったサブジェクト名をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="46ea0-118">BizTalk Adapter for TIBCO Rendezvous does not support subject names containing those characters.</span></span>  
  
- <span data-ttu-id="46ea0-119">デーモンへのセキュリティで保護された接続はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="46ea0-119">Secure connection to daemons is not supported.</span></span>  
  
- <span data-ttu-id="46ea0-120">カスタム データ型はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="46ea0-120">Custom data types are not supported.</span></span>  
  
- <span data-ttu-id="46ea0-121">認定メッセージングは送信側ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="46ea0-121">Certified Messaging is not supported on the transmit side.</span></span>  
- 
  ## <a name="next-step"></a><span data-ttu-id="46ea0-122">次の手順</span><span class="sxs-lookup"><span data-stu-id="46ea0-122">Next step</span></span>

[<span data-ttu-id="46ea0-123">チュートリアル:TIBCO Rendezvous の Microsoft BizTalk Adapter の使用</span><span class="sxs-lookup"><span data-stu-id="46ea0-123">Tutorials: Using the Microsoft BizTalk Adapter for TIBCO Rendezvous</span></span>](../core/tutorials-using-the-microsoft-biztalk-adapter-for-tibco-rendezvous.md)  