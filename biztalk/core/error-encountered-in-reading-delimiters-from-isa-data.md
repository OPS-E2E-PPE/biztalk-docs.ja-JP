---
title: ISA データから区切り記号を読み取り中に発生したエラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8cb60abd-53c8-45e1-a840-d27dc974aad7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3cb0dac30c18cb2c6da9c5a57818ce301fe95ec
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015739"
---
# <a name="error-encountered-in-reading-delimiters-from-isa-data"></a><span data-ttu-id="0a7dc-102">ISA データから区切り記号を読み取り中にエラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="0a7dc-102">Error encountered in reading delimiters from ISA data</span></span>
## <a name="details"></a><span data-ttu-id="0a7dc-103">詳細</span><span class="sxs-lookup"><span data-stu-id="0a7dc-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="0a7dc-104">製品名</span><span class="sxs-lookup"><span data-stu-id="0a7dc-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="0a7dc-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="0a7dc-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="0a7dc-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0a7dc-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="0a7dc-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="0a7dc-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0a7dc-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="0a7dc-108"> EDI</span></span> |
|    <span data-ttu-id="0a7dc-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0a7dc-109">Component</span></span>    |                                       <span data-ttu-id="0a7dc-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="0a7dc-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="0a7dc-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="0a7dc-111">Symbolic Name</span></span>  |                                     <span data-ttu-id="0a7dc-112">InvalidIsaData</span><span class="sxs-lookup"><span data-stu-id="0a7dc-112">InvalidIsaData</span></span>                                     |
|  <span data-ttu-id="0a7dc-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="0a7dc-113">Message Text</span></span>   |                 <span data-ttu-id="0a7dc-114">ISA データから区切り記号を読み取り中にエラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="0a7dc-114">Error encountered in reading delimiters from ISA data</span></span>                  |
  
## <a name="explanation"></a><span data-ttu-id="0a7dc-115">説明</span><span class="sxs-lookup"><span data-stu-id="0a7dc-115">Explanation</span></span>  
 <span data-ttu-id="0a7dc-116">このエラー/警告/情報イベントは、ISA セグメントからの区切り記号を解析できなかったため、受信 X12 インターチェンジの処理中に EDI 受信パイプラインでエラーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="0a7dc-116">This Error/Warning/Information event indicates that the EDI receive pipeline encountered an error when processing an incoming X12 interchange because it could not parse the separators from the ISA segment.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0a7dc-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="0a7dc-117">User Action</span></span>  
 <span data-ttu-id="0a7dc-118">このエラーを解決するには、受信インターチェンジの ISA セグメントの区切り記号が一意で有効であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0a7dc-118">To resolve this error, verify that the separators in the ISA segment of the incoming interchange are unique and valid.</span></span> <span data-ttu-id="0a7dc-119">そうでない場合は、インターチェンジの送信者に対して、区切り記号の各フィールド (繰り返し区切り記号の場合は ISA11 セグメント、コンポーネント区切り記号の場合は ISA16 セグメント) に一意で有効な値を入力してから、インターチェンジを再送信するように依頼します。</span><span class="sxs-lookup"><span data-stu-id="0a7dc-119">If not, have the sender of the interchange enter unique and valid values into each of the separator fields (the ISA11 segment for the repetition separator and the ISA16 segment for the component separator), and then resend the interchange.</span></span>