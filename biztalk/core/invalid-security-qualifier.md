---
title: 無効なセキュリティ修飾子 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dce36f4b-ab59-41c0-8b92-3020f6393db9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f4d16b4295bd8d01f93db964d4e45e8363205ee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257530"
---
# <a name="invalid-security-qualifier"></a><span data-ttu-id="8455f-102">セキュリティ修飾子が無効です</span><span class="sxs-lookup"><span data-stu-id="8455f-102">Invalid Security Qualifier</span></span>
## <a name="details"></a><span data-ttu-id="8455f-103">詳細</span><span class="sxs-lookup"><span data-stu-id="8455f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8455f-104">製品名</span><span class="sxs-lookup"><span data-stu-id="8455f-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="8455f-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="8455f-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="8455f-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="8455f-106">Event ID</span></span>|-|  
|<span data-ttu-id="8455f-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="8455f-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="8455f-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="8455f-108"> EDI</span></span>|  
|<span data-ttu-id="8455f-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8455f-109">Component</span></span>|<span data-ttu-id="8455f-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="8455f-110">EDI Engine</span></span>|  
|<span data-ttu-id="8455f-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="8455f-111">Symbolic Name</span></span>|<span data-ttu-id="8455f-112">X12Ta1InvalidSecurityQualifierDescription</span><span class="sxs-lookup"><span data-stu-id="8455f-112">X12Ta1InvalidSecurityQualifierDescription</span></span>|  
|<span data-ttu-id="8455f-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="8455f-113">Message Text</span></span>|<span data-ttu-id="8455f-114">セキュリティ修飾子が無効です</span><span class="sxs-lookup"><span data-stu-id="8455f-114">Invalid Security Qualifier</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8455f-115">説明</span><span class="sxs-lookup"><span data-stu-id="8455f-115">Explanation</span></span>  
 <span data-ttu-id="8455f-116">このエラー/警告/情報イベントは、ISA03 フィールドのセキュリティ修飾子または UNB6.2 フィールドの受信者の参照/パスワードの修飾子が、サービス スキーマ (BaseArtifacts.dll 内の X12ServiceSchema または EdifactServiceSchema) で設定された列挙の値に一致しなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="8455f-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the Security Qualifier in the ISA03 field or the Recipient Reference Password Qualifier in the UNB6.2 field did not match a value in the enumeration established by the service schema (X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8455f-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="8455f-117">User Action</span></span>  
 <span data-ttu-id="8455f-118">このエラーを解決するには、ISA03 フィールドまたは UNB6.2 フィールドが、サービス スキーマで設定されている列挙のいずれかの値と一致するようにします。</span><span class="sxs-lookup"><span data-stu-id="8455f-118">To resolve this error, make sure that the ISA03 field or the UNB6.2 field matches one of the values in the enumeration established by the service schema.</span></span> <span data-ttu-id="8455f-119">インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="8455f-119">Have the interchange resent.</span></span>