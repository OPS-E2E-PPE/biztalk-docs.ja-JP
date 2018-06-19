---
title: スキーマが見つかりませんでしたとしてメッセージをシリアル化できません |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 37897c04-650d-4695-846d-b8ba61365647
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b887d4a07d7a461278d3858289882a9ce441e9e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262674"
---
# <a name="message-cannot-be-serialized-as-the-schema-could-not-be-located"></a><span data-ttu-id="26fa8-102">スキーマが見つからなかったため、メッセージをシリアル化できません</span><span class="sxs-lookup"><span data-stu-id="26fa8-102">Message cannot be serialized as the schema could not be located</span></span>
## <a name="details"></a><span data-ttu-id="26fa8-103">詳細</span><span class="sxs-lookup"><span data-stu-id="26fa8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="26fa8-104">製品名</span><span class="sxs-lookup"><span data-stu-id="26fa8-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="26fa8-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="26fa8-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="26fa8-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="26fa8-106">Event ID</span></span>|-|  
|<span data-ttu-id="26fa8-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="26fa8-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="26fa8-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="26fa8-108"> EDI</span></span>|  
|<span data-ttu-id="26fa8-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="26fa8-109">Component</span></span>|<span data-ttu-id="26fa8-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="26fa8-110">EDI Engine</span></span>|  
|<span data-ttu-id="26fa8-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="26fa8-111">Symbolic Name</span></span>|<span data-ttu-id="26fa8-112">MessageSerializationFailureDueToMissingSchema</span><span class="sxs-lookup"><span data-stu-id="26fa8-112">MessageSerializationFailureDueToMissingSchema</span></span>|  
|<span data-ttu-id="26fa8-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="26fa8-113">Message Text</span></span>|<span data-ttu-id="26fa8-114">スキーマ {0} が見つからなかったため、メッセージをシリアル化できません。</span><span class="sxs-lookup"><span data-stu-id="26fa8-114">Message can not be serialized as the schema {0} could not be located.</span></span> <span data-ttu-id="26fa8-115">スキーマが展開されていないか、複数のコピーが展開されています。</span><span class="sxs-lookup"><span data-stu-id="26fa8-115">Either the schema is not deployed or multiple copies are deployed.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="26fa8-116">説明</span><span class="sxs-lookup"><span data-stu-id="26fa8-116">Explanation</span></span>  
 <span data-ttu-id="26fa8-117">このエラー/警告/情報イベントは、インターチェンジのシリアル化に使用するために必要なスキーマを確認できなかったため、送信パイプラインで送信インターチェンジをシリアル化できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="26fa8-117">This Error/Warning/Information event indicates that the send pipeline could not serialize the outgoing interchange because the pipeline could not determine the schema that it needed to use to serialize the interchange.</span></span> <span data-ttu-id="26fa8-118">スキーマが展開されていないか、スキーマの複数のコピーが展開されています。</span><span class="sxs-lookup"><span data-stu-id="26fa8-118">The schema was either not deployed or multiple copies of the schema were deployed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="26fa8-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="26fa8-119">User Action</span></span>  
 <span data-ttu-id="26fa8-120">このエラーを解決するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="26fa8-120">To resolve this error, do one of the following:</span></span>  
  
1.  <span data-ttu-id="26fa8-121">インターチェンジに関連付けられたスキーマが展開されていない場合は、Visual Studio を開き、BizTalk プロジェクトにスキーマを追加してから、プロジェクトをビルドして展開します。</span><span class="sxs-lookup"><span data-stu-id="26fa8-121">If the schema associated with the interchange has not been deployed, open Visual Studio, add the schema to a BizTalk project, and then build and deploy the project.</span></span>  
  
2.  <span data-ttu-id="26fa8-122">スキーマの複数のコピーが展開されている場合は、Visual Studio を開き、インターチェンジに関連付けられたスキーマの 1 つを残してその他すべてを展開解除します。</span><span class="sxs-lookup"><span data-stu-id="26fa8-122">If more than one copy of the schema has been deployed, open Visual Studio, and undeploy all but one of the copies of the schema associated with the interchange.</span></span>