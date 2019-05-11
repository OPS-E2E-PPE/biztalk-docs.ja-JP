---
title: フィールドの区切り記号の後、セグメント タグ id が見つかりません |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5f6f0a74-3560-4d6d-9893-85e8426e6b17
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd70d335970d241099b305646ed13a83bbcfbd34
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388071"
---
# <a name="field-separator-not-found-after-segment-tag-id"></a><span data-ttu-id="82a20-102">セグメント タグ ID の後にフィールドの区切り記号が見つかりません</span><span class="sxs-lookup"><span data-stu-id="82a20-102">Field separator not found after segment tag id</span></span>
## <a name="details"></a><span data-ttu-id="82a20-103">詳細</span><span class="sxs-lookup"><span data-stu-id="82a20-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="82a20-104">製品名</span><span class="sxs-lookup"><span data-stu-id="82a20-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="82a20-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="82a20-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="82a20-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="82a20-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="82a20-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="82a20-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="82a20-108">EDI</span><span class="sxs-lookup"><span data-stu-id="82a20-108">EDI</span></span> |
|    <span data-ttu-id="82a20-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="82a20-109">Component</span></span>    |                                       <span data-ttu-id="82a20-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="82a20-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="82a20-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="82a20-111">Symbolic Name</span></span>  |                          <span data-ttu-id="82a20-112">X12SeFsNotFoundAfterTagIdDescription</span><span class="sxs-lookup"><span data-stu-id="82a20-112">X12SeFsNotFoundAfterTagIdDescription</span></span>                          |
|  <span data-ttu-id="82a20-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="82a20-113">Message Text</span></span>   |                     <span data-ttu-id="82a20-114">セグメント タグ ID の後にフィールドの区切り記号が見つかりません</span><span class="sxs-lookup"><span data-stu-id="82a20-114">Field separator not found after segment tag id</span></span>                     |
  
## <a name="explanation"></a><span data-ttu-id="82a20-115">説明</span><span class="sxs-lookup"><span data-stu-id="82a20-115">Explanation</span></span>  
 <span data-ttu-id="82a20-116">このエラー/警告/情報イベントは、インターチェンジに含まれているセグメントでセグメント識別子が使用されており、その直後にデータ要素区切り記号が続いていなかったため、受信パイプラインでインターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="82a20-116">This Error/Warning/Information event indicates that the receive pipeline could not process the interchange because the interchange contained a segment that had a segment identifier without a data element separator immediately following it.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="82a20-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="82a20-117">User Action</span></span>  
 <span data-ttu-id="82a20-118">このエラーを解決するには、インターチェンジのすべてのセグメント識別子の直後にデータ要素区切り記号が続いていることを確認し、インターチェンジを再送信してもらいます。</span><span class="sxs-lookup"><span data-stu-id="82a20-118">To resolve this error, ensure that all segment identifiers in the interchange have data element separators immediately following them, and then have the interchange resent.</span></span>