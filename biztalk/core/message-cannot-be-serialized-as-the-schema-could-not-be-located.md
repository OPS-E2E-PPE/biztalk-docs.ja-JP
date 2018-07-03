---
title: スキーマが見つからなかったために、メッセージがシリアル化ことはできません |Microsoft Docs
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
ms.openlocfilehash: 1f366fc619ac070d618345ce6bde9996710b1242
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988187"
---
# <a name="message-cannot-be-serialized-as-the-schema-could-not-be-located"></a><span data-ttu-id="c2d58-102">スキーマが見つからなかったため、メッセージをシリアル化できません</span><span class="sxs-lookup"><span data-stu-id="c2d58-102">Message cannot be serialized as the schema could not be located</span></span>
## <a name="details"></a><span data-ttu-id="c2d58-103">詳細</span><span class="sxs-lookup"><span data-stu-id="c2d58-103">Details</span></span>  
  
|                 |                                                                                                                                          |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="c2d58-104">製品名</span><span class="sxs-lookup"><span data-stu-id="c2d58-104">Product Name</span></span>   |                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                            |
| <span data-ttu-id="c2d58-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c2d58-105">Product Version</span></span> |                                        [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                        |
|    <span data-ttu-id="c2d58-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c2d58-106">Event ID</span></span>     |                                                                    -                                                                     |
|  <span data-ttu-id="c2d58-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c2d58-107">Event Source</span></span>   |                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c2d58-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="c2d58-108"> EDI</span></span>                          |
|    <span data-ttu-id="c2d58-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c2d58-109">Component</span></span>    |                                                                <span data-ttu-id="c2d58-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="c2d58-110">EDI Engine</span></span>                                                                |
|  <span data-ttu-id="c2d58-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c2d58-111">Symbolic Name</span></span>  |                                              <span data-ttu-id="c2d58-112">MessageSerializationFailureDueToMissingSchema</span><span class="sxs-lookup"><span data-stu-id="c2d58-112">MessageSerializationFailureDueToMissingSchema</span></span>                                               |
|  <span data-ttu-id="c2d58-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c2d58-113">Message Text</span></span>   | <span data-ttu-id="c2d58-114">メッセージがスキーマとしてシリアル化しないできる{0}配置されていることができませんでした。</span><span class="sxs-lookup"><span data-stu-id="c2d58-114">Message can not be serialized as the schema {0} could not be located.</span></span> <span data-ttu-id="c2d58-115">スキーマが展開されていないか、複数のコピーが展開されています。</span><span class="sxs-lookup"><span data-stu-id="c2d58-115">Either the schema is not deployed or multiple copies are deployed.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="c2d58-116">説明</span><span class="sxs-lookup"><span data-stu-id="c2d58-116">Explanation</span></span>  
 <span data-ttu-id="c2d58-117">このエラー/警告/情報イベントは、インターチェンジのシリアル化に使用するために必要なスキーマを確認できなかったため、送信パイプラインで送信インターチェンジをシリアル化できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="c2d58-117">This Error/Warning/Information event indicates that the send pipeline could not serialize the outgoing interchange because the pipeline could not determine the schema that it needed to use to serialize the interchange.</span></span> <span data-ttu-id="c2d58-118">スキーマが展開されていないか、スキーマの複数のコピーが展開されています。</span><span class="sxs-lookup"><span data-stu-id="c2d58-118">The schema was either not deployed or multiple copies of the schema were deployed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c2d58-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c2d58-119">User Action</span></span>  
 <span data-ttu-id="c2d58-120">このエラーを解決するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c2d58-120">To resolve this error, do one of the following:</span></span>  
  
1.  <span data-ttu-id="c2d58-121">インターチェンジに関連付けられたスキーマが展開されていない場合は、Visual Studio を開き、BizTalk プロジェクトにスキーマを追加してから、プロジェクトをビルドして展開します。</span><span class="sxs-lookup"><span data-stu-id="c2d58-121">If the schema associated with the interchange has not been deployed, open Visual Studio, add the schema to a BizTalk project, and then build and deploy the project.</span></span>  
  
2.  <span data-ttu-id="c2d58-122">スキーマの複数のコピーが展開されている場合は、Visual Studio を開き、インターチェンジに関連付けられたスキーマの 1 つを残してその他すべてを展開解除します。</span><span class="sxs-lookup"><span data-stu-id="c2d58-122">If more than one copy of the schema has been deployed, open Visual Studio, and undeploy all but one of the copies of the schema associated with the interchange.</span></span>