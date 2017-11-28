---
title: "ISA セグメントは、108 の最小長を持つ必要があります |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57641445-cebb-4219-998d-54038d7ddf19
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ecd5c6761c6dbcc59ad6353efa2772b9eecf387
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="isa-segment-needs-to-have-a-minimum-length-of-108"></a><span data-ttu-id="d6b30-102">ISA セグメントは、108 文字以上の文字列から構成されている必要があります</span><span class="sxs-lookup"><span data-stu-id="d6b30-102">ISA segment needs to have a minimum length of 108</span></span>
## <a name="details"></a><span data-ttu-id="d6b30-103">詳細</span><span class="sxs-lookup"><span data-stu-id="d6b30-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d6b30-104">製品名</span><span class="sxs-lookup"><span data-stu-id="d6b30-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="d6b30-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d6b30-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="d6b30-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d6b30-106">Event ID</span></span>|-|  
|<span data-ttu-id="d6b30-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d6b30-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d6b30-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="d6b30-108"> EDI</span></span>|  
|<span data-ttu-id="d6b30-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d6b30-109">Component</span></span>|<span data-ttu-id="d6b30-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="d6b30-110">EDI Engine</span></span>|  
|<span data-ttu-id="d6b30-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d6b30-111">Symbolic Name</span></span>|<span data-ttu-id="d6b30-112">NseIsaSuffix1LFDescription</span><span class="sxs-lookup"><span data-stu-id="d6b30-112">NseIsaSuffix1LFDescription</span></span>|  
|<span data-ttu-id="d6b30-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d6b30-113">Message Text</span></span>|<span data-ttu-id="d6b30-114">ISA セグメントは、108 文字以上の文字列から構成されている必要があります。インスタンスに格納されている文字の数は {0} 文字です。</span><span class="sxs-lookup"><span data-stu-id="d6b30-114">ISA segment needs to have a minimum length of 108, instance has {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d6b30-115">説明</span><span class="sxs-lookup"><span data-stu-id="d6b30-115">Explanation</span></span>  
 <span data-ttu-id="d6b30-116">このエラー/警告/情報イベントは、インターチェンジの ISA セグメントがサービス スキーマ (BaseArtifacts.dll 内の X12ServiceSchema または EdifactServiceSchema) で設定された桁数に準拠していなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="d6b30-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the ISA segment in the interchange did not conform to the number of digits established by the service schema (X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d6b30-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d6b30-117">User Action</span></span>  
 <span data-ttu-id="d6b30-118">このエラーを解決するには、ISA セグメント (ISA01 から ISA16 まで) の各フィールドに必要な最小桁数が含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d6b30-118">To resolve this error, make sure that each of the fields in the ISA segment (from ISA01 to ISA16) has the required minimum number of digits.</span></span> <span data-ttu-id="d6b30-119">最小桁数を確認するには、BizTalk Server 管理コンソールを開き、[BizTalk グループ] ノードを開きます。次に、[アプリケーション] ノード、[BizTalk EDI アプリケーション] ノード、スキーマ ノードの順に開き、ISA のルート ノードで Microsoft.BizTalk.Edi.BaseArtifacts.X12ServiceSchema を開いて、[スキーマ ビュー] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d6b30-119">You can see the minimum number of digits by opening the BizTalk Server Administration Console; opening the BizTalk Group node, the Applications node, the BizTalk EDI Application node, and then the schema node; opening the Microsoft.BizTalk.Edi.BaseArtifacts.X12ServiceSchema with the root node of ISA; and then clicking the Schema View.</span></span>