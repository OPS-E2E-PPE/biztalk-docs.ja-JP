---
title: "アグリーメントにアクセスできません受信者 id を使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 470325f4-abc4-40bb-9109-9ffc73b496df
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f41b126ca0ebb96716f21381d2e1681ea59bd414
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="unable-to-access-agreement-using-receiver-identity"></a><span data-ttu-id="5217f-102">受信者 ID を使用してアグリーメントにアクセスできません</span><span class="sxs-lookup"><span data-stu-id="5217f-102">Unable to access agreement using receiver identity</span></span>
## <a name="details"></a><span data-ttu-id="5217f-103">詳細</span><span class="sxs-lookup"><span data-stu-id="5217f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5217f-104">製品名</span><span class="sxs-lookup"><span data-stu-id="5217f-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="5217f-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="5217f-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="5217f-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="5217f-106">Event ID</span></span>|-|  
|<span data-ttu-id="5217f-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="5217f-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="5217f-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="5217f-108"> EDI</span></span>|  
|<span data-ttu-id="5217f-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5217f-109">Component</span></span>|<span data-ttu-id="5217f-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="5217f-110">AS2 Engine</span></span>|  
|<span data-ttu-id="5217f-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="5217f-111">Symbolic Name</span></span>|<span data-ttu-id="5217f-112">UnableToLocateAS2PartyByPartyNameError</span><span class="sxs-lookup"><span data-stu-id="5217f-112">UnableToLocateAS2PartyByPartyNameError</span></span>|  
|<span data-ttu-id="5217f-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="5217f-113">Message Text</span></span>|<span data-ttu-id="5217f-114">アグリーメントにアクセスできません受信者 id を使用して: {0}</span><span class="sxs-lookup"><span data-stu-id="5217f-114">Unable to access agreement using receiver identity: {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5217f-115">説明</span><span class="sxs-lookup"><span data-stu-id="5217f-115">Explanation</span></span>  
 <span data-ttu-id="5217f-116">このエラーは、送信パイプラインで送信 AS2 メッセージの送信先パーティを決定できなかったことを示します。送信パイプラインは、送信メッセージの AS2To コンテキスト プロパティまたは Http.UserHttpHeaders コンテキスト プロパティの AS2To プロパティと、[AS2 のプロパティ] ダイアログ ボックスの [パーティ - AS2 メッセージの受信者] ページにある AS2-To プロパティのパーティの名前を照合できませんでした。</span><span class="sxs-lookup"><span data-stu-id="5217f-116">This error indicates that the send pipeline could not determine the party for an outgoing AS2 message because it could not match the AS2To context property of the outbound message or the AS2To property in the Http.UserHttpHeaders context property with the name of the party in the AS2-To property in the Party as AS2 Message Receiver page of the AS2 Properties dialog box.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5217f-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="5217f-117">User Action</span></span>  
 <span data-ttu-id="5217f-118">このエラーを解決するには、[AS2 のプロパティ] ダイアログ ボックスの [パーティ - AS2 メッセージの受信者] ページにある AS2-To プロパティを、エラーになった AS2 メッセージに関連付けられた適切なパーティ名に設定します。</span><span class="sxs-lookup"><span data-stu-id="5217f-118">To resolve this error, set the AS2-To property in the Party as AS2 Message Receiver page of the AS2 Properties dialog box to the appropriate party name associated with the AS2 message that is in error.</span></span>