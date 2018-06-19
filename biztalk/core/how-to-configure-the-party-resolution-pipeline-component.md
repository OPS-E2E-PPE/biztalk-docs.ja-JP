---
title: パーティの解決パイプライン コンポーネントを構成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- authenticating, Partner Management
- Party Resolution [pipeline component], configuring
- Partner Management, authenticating
- pipeline components, Party Resolution
ms.assetid: 0ebd30f7-3a6b-4457-8e30-80bf81fbd28d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0c78792cd7c61ed1297954625fbd7da5aedfa04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248218"
---
# <a name="how-to-configure-the-party-resolution-pipeline-component"></a><span data-ttu-id="072ac-102">パーティの解決パイプライン コンポーネントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="072ac-102">How to Configure the Party Resolution Pipeline Component</span></span>
<span data-ttu-id="072ac-103">パーティの解決パイプライン コンポーネントは、クライアントのユーザー セキュリティ ID および証明書のサブジェクトを BizTalk Server パーティにマップするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="072ac-103">The Party Resolution pipeline component is used to map the user security ID and the certificate subject for the client to a BizTalk Server party.</span></span> <span data-ttu-id="072ac-104">マッピングを使用して、BizTalk Server にメッセージを送信したパーティの認証を行います。</span><span class="sxs-lookup"><span data-stu-id="072ac-104">The mapping is used to enforce authentication of the parties who send messages to BizTalk Server.</span></span> <span data-ttu-id="072ac-105">パートナー管理の詳細については、次を参照してください。[アグリーメントを作成する方法](http://msdn.microsoft.com/library/f8608cf7-8ac5-4f02-805e-5a0bdf19ca8c)です。</span><span class="sxs-lookup"><span data-stu-id="072ac-105">For more information about partner management, see[How to Create an Agreement](http://msdn.microsoft.com/library/f8608cf7-8ac5-4f02-805e-5a0bdf19ca8c).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="072ac-106">パーティの解決パイプライン コンポーネントで Windows ユーザーを検証できるようにするには、パーティに WindowsUser エイリアスを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="072ac-106">To enable the Party Resolution pipeline component to validate a Windows user, you must add the WindowsUser alias to a party.</span></span> <span data-ttu-id="072ac-107">詳細については、次を参照してください。[パーティの解決パイプライン コンポーネント](../core/party-resolution-pipeline-component.md)です。</span><span class="sxs-lookup"><span data-stu-id="072ac-107">For more information, see [Party Resolution Pipeline Component](../core/party-resolution-pipeline-component.md).</span></span>  
  
### <a name="to-configure-the-properties-for-the-party-resolution-pipeline-component"></a><span data-ttu-id="072ac-108">パーティの解決パイプライン コンポーネントのプロパティを構成するには</span><span class="sxs-lookup"><span data-stu-id="072ac-108">To configure the properties for the Party Resolution pipeline component</span></span>  
  
1.  <span data-ttu-id="072ac-109">パーティの解決パイプライン コンポーネントを、受信パイプラインのパーティの解決ステージにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="072ac-109">Drag the Party Resolution pipeline component into the ResolveParty stage of a receive pipeline.</span></span>  
  
2.  <span data-ttu-id="072ac-110">[プロパティ] ウィンドウでの**パイプライン コンポーネントのプロパティ**セクションで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="072ac-110">In the Properties window, in the **Pipeline Component Properties** section, do the following.</span></span>  
  
    |<span data-ttu-id="072ac-111">プロパティ</span><span class="sxs-lookup"><span data-stu-id="072ac-111">Use this</span></span>|<span data-ttu-id="072ac-112">目的</span><span class="sxs-lookup"><span data-stu-id="072ac-112">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="072ac-113">**証明書によるパーティを解決します。**</span><span class="sxs-lookup"><span data-stu-id="072ac-113">**Resolve Party By Certificate**</span></span>|<span data-ttu-id="072ac-114">設定**True**メッセージの受信場所からパーティから署名証明書の拇印に基づいてパーティの解決を有効にする場合。</span><span class="sxs-lookup"><span data-stu-id="072ac-114">Set to **True** if you want to enable party resolution based on the thumbprint of the signature certificate from the party from where the messages are received.</span></span><br /><br /> <span data-ttu-id="072ac-115">既定値:**は True。**</span><span class="sxs-lookup"><span data-stu-id="072ac-115">Default value: **True**</span></span>|  
    |<span data-ttu-id="072ac-116">**SID によるパーティを解決します。**</span><span class="sxs-lookup"><span data-stu-id="072ac-116">**Resolve Party By SID**</span></span>|<span data-ttu-id="072ac-117">設定**True**センダ アカウントのセキュリティ識別子 (SID) に基づいたパーティの解決を有効にする場合。</span><span class="sxs-lookup"><span data-stu-id="072ac-117">Set to **True** if you want to enable party resolution based on the security identifier (SID) of the sender account.</span></span><br /><br /> <span data-ttu-id="072ac-118">両方のプロパティが設定されている場合**True**、**証明書によるパーティを解決するには**プロパティよりも優先、 **SID によるパーティの解決**を場合は、両方を意味するプロパティ、証明書と SID が使用可能な証明書のサブジェクトが使用されます。</span><span class="sxs-lookup"><span data-stu-id="072ac-118">If both properties are set to **True**, the **Resolve Party By Certificate** property takes precedence over the **Resolve Party By SID** property, meaning that if both the certificate and the SID are available, the certificate subject is used.</span></span> <span data-ttu-id="072ac-119">証明書のサブジェクトを使用して、パーティを解決できない場合、コンポーネントにフォールバックすること、 **SID によるパーティの解決**のスタンプは、プロパティ、および既定値 (s-1-5 ~ 7) **BTS です。SourcePartyID**です。</span><span class="sxs-lookup"><span data-stu-id="072ac-119">If the party cannot be resolved by using the certificate subject, the component does not fall back to the **Resolve Party By SID** property, and the default value (s-1-5-7) is stamped for **BTS.SourcePartyID**.</span></span><br /><br /> <span data-ttu-id="072ac-120">既定値:**は True。**</span><span class="sxs-lookup"><span data-stu-id="072ac-120">Default value: **True**</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="072ac-121">ユーザー名に基づいて、BizTalk メッセージ キュー アダプタと、パーティの解決を使用する場合、設定**証明書によるパーティを解決するには**に**False**と**SID によるパーティの解決**に**True**です。</span><span class="sxs-lookup"><span data-stu-id="072ac-121">If you use the BizTalk Message Queuing adapter and want to resolve the party based on user name, set **Resolve Party By Certificate** to **False** and **Resolve Party By SID** to **True**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="072ac-122">参照</span><span class="sxs-lookup"><span data-stu-id="072ac-122">See Also</span></span>  
 <span data-ttu-id="072ac-123">[パーティの解決パイプライン コンポーネント](../core/party-resolution-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="072ac-123">[Party Resolution Pipeline Component](../core/party-resolution-pipeline-component.md) </span></span>  
 <span data-ttu-id="072ac-124">[ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="072ac-124">[Configuring Native Pipeline Components](../core/configuring-native-pipeline-components.md) </span></span>  
 [<span data-ttu-id="072ac-125">カスタム パーティの解決 (BizTalk Server サンプル)</span><span class="sxs-lookup"><span data-stu-id="072ac-125">Custom Party Resolution (BizTalk Server Sample)</span></span>](../core/custom-party-resolution-biztalk-server-sample.md)