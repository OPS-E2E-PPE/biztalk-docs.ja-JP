---
title: 無効な制御標準識別子 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d2b5a54-7f29-49c9-8bcf-a5b4b6d07ad3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5af73589799876babc75caab3730f7de7c33914
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381370"
---
# <a name="invalid-control-standard-identifier"></a><span data-ttu-id="0425a-102">制御標準識別子が無効です</span><span class="sxs-lookup"><span data-stu-id="0425a-102">Invalid Control Standard Identifier</span></span>
## <a name="details"></a><span data-ttu-id="0425a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="0425a-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="0425a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="0425a-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="0425a-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="0425a-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="0425a-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0425a-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="0425a-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="0425a-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="0425a-108">EDI</span><span class="sxs-lookup"><span data-stu-id="0425a-108">EDI</span></span> |
|    <span data-ttu-id="0425a-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0425a-109">Component</span></span>    |                                       <span data-ttu-id="0425a-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="0425a-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="0425a-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="0425a-111">Symbolic Name</span></span>  |                   <span data-ttu-id="0425a-112">X12Ta1InvalidControlStandardIdentifierDescription</span><span class="sxs-lookup"><span data-stu-id="0425a-112">X12Ta1InvalidControlStandardIdentifierDescription</span></span>                    |
|  <span data-ttu-id="0425a-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="0425a-113">Message Text</span></span>   |                          <span data-ttu-id="0425a-114">制御標準識別子が無効です</span><span class="sxs-lookup"><span data-stu-id="0425a-114">Invalid Control Standard Identifier</span></span>                           |
  
## <a name="explanation"></a><span data-ttu-id="0425a-115">説明</span><span class="sxs-lookup"><span data-stu-id="0425a-115">Explanation</span></span>  
 <span data-ttu-id="0425a-116">このエラー/警告/情報イベントは、インターチェンジ内のインターチェンジ制御標準識別子 (フィールド ISA11) が、スキーマで指定されている列挙のエントリと一致しなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="0425a-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of the interchange control standards identifier (field ISA11) in the interchange did not match an entry in the enumeration specified by the schema.</span></span> <span data-ttu-id="0425a-117">スキーマは、BaseArtifacts.dll 内の X12ServiceSchema または EdifactServiceSchema です。</span><span class="sxs-lookup"><span data-stu-id="0425a-117">The schema is the X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0425a-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="0425a-118">User Action</span></span>  
 <span data-ttu-id="0425a-119">このエラーを解決するには、インターチェンジで使用されているインターチェンジ制御標準識別子が ISA11 フィールドの列挙のエントリと一致していることを確認し、インターチェンジを再送信してもらいます。</span><span class="sxs-lookup"><span data-stu-id="0425a-119">To resolve this error, make sure that the interchange control standards identifier used in the interchange matches an entry in the enumeration for the ISA11 field, and then have the interchange resent.</span></span>