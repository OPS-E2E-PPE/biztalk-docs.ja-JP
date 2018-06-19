---
title: 無効なセキュリティ値 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ee380da7-c05e-4b9b-84ee-f7ffee90eb0e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e41315400ee2b0eae099439237356b61676b26cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257210"
---
# <a name="invalid-security-value"></a><span data-ttu-id="99a07-102">セキュリティの値が無効です</span><span class="sxs-lookup"><span data-stu-id="99a07-102">Invalid Security Value</span></span>
## <a name="details"></a><span data-ttu-id="99a07-103">詳細</span><span class="sxs-lookup"><span data-stu-id="99a07-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="99a07-104">製品名</span><span class="sxs-lookup"><span data-stu-id="99a07-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="99a07-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="99a07-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="99a07-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="99a07-106">Event ID</span></span>|-|  
|<span data-ttu-id="99a07-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="99a07-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="99a07-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="99a07-108"> EDI</span></span>|  
|<span data-ttu-id="99a07-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="99a07-109">Component</span></span>|<span data-ttu-id="99a07-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="99a07-110">EDI Engine</span></span>|  
|<span data-ttu-id="99a07-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="99a07-111">Symbolic Name</span></span>|<span data-ttu-id="99a07-112">X12Ta1InvalidSecurityValueDescription</span><span class="sxs-lookup"><span data-stu-id="99a07-112">X12Ta1InvalidSecurityValueDescription</span></span>|  
|<span data-ttu-id="99a07-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="99a07-113">Message Text</span></span>|<span data-ttu-id="99a07-114">セキュリティの値が無効です</span><span class="sxs-lookup"><span data-stu-id="99a07-114">Invalid Security Value</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="99a07-115">説明</span><span class="sxs-lookup"><span data-stu-id="99a07-115">Explanation</span></span>  
 <span data-ttu-id="99a07-116">このエラー/警告/情報イベントは、ISA04 フィールドのセキュリティ情報または UNB6.1 フィールドの受信者の参照/パスワードの値が、サービス スキーマ (BaseArtifacts.dll 内の X12ServiceSchema または EdifactServiceSchema) で設定されたデータ型と桁数に準拠していなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="99a07-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the Security Information in the ISA04 field or the Recipient Reference Password Value in the UNB6.1 field did not conform to the data type and number of digits established by the service schema (X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="99a07-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="99a07-117">User Action</span></span>  
 <span data-ttu-id="99a07-118">このエラーを解決するには、ISA04 フィールドが X12_AN データ型で、長さが 10 桁 (末尾のスペースの有無とは無関係) であるか、または UNB6.1 フィールドが EDIFACT_AN データ型で、長さが 1 ～ 14 文字の範囲であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="99a07-118">To resolve this error, make sure that the ISA04 field is of the X12_AN data type and is 10 characters long (with or without trailing spaces) or that the UNB6.1 field is of the EDIFACT_AN data type and is between 1 and 14 characters long.</span></span> <span data-ttu-id="99a07-119">インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="99a07-119">Have the interchange resent.</span></span>