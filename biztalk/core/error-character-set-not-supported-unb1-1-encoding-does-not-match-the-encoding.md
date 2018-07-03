---
title: 文字セットの UNB1.1 のエンコード情報では、実際のエンコードは一致しないために、サポートされていません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 085ea8e3-e0d8-45bd-9985-6787b00e4d5a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ef85488281c6ddd7fe8ecdb0f096a21bbc30c06
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978387"
---
# <a name="character-set-not-supported-because-the-encoding-information-in-unb11-does-not-match-the-actual-encoding"></a><span data-ttu-id="49667-102">UNB1.1 のエンコード情報が実際のエンコードと一致しないため、文字セットはサポートされません</span><span class="sxs-lookup"><span data-stu-id="49667-102">Character set not supported because the encoding information in UNB1.1 does not match the actual encoding</span></span>
## <a name="details"></a><span data-ttu-id="49667-103">詳細</span><span class="sxs-lookup"><span data-stu-id="49667-103">Details</span></span>  
  
|                 |                                                                                                                                                     |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="49667-104">製品名</span><span class="sxs-lookup"><span data-stu-id="49667-104">Product Name</span></span>   |                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                  |
| <span data-ttu-id="49667-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="49667-105">Product Version</span></span> |                                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                              |
|    <span data-ttu-id="49667-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="49667-106">Event ID</span></span>     |                                                                          -                                                                          |
|  <span data-ttu-id="49667-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="49667-107">Event Source</span></span>   |                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="49667-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="49667-108"> EDI</span></span>                                |
|    <span data-ttu-id="49667-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="49667-109">Component</span></span>    |                                                                     <span data-ttu-id="49667-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="49667-110">EDI Engine</span></span>                                                                      |
|  <span data-ttu-id="49667-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="49667-111">Symbolic Name</span></span>  |                                                                          -                                                                          |
|  <span data-ttu-id="49667-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="49667-112">Message Text</span></span>   | <span data-ttu-id="49667-113">文字セットがサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="49667-113">Character set not supported.</span></span> <span data-ttu-id="49667-114">UNB1.1 のエンコード情報が実際のインターチェンジのエンコードと一致しないことが原因の可能性があります。</span><span class="sxs-lookup"><span data-stu-id="49667-114">It could be due to the fact that encoding information in UNB1.1 does not match the actual encoding of the interchange.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="49667-115">説明</span><span class="sxs-lookup"><span data-stu-id="49667-115">Explanation</span></span>  
 <span data-ttu-id="49667-116">このエラー/警告/情報イベントは、インターチェンジで使用されている文字がインターチェンジの UNB1.1 で識別されている文字セットに一致しないため、EDI 受信パイプラインで受信 EDIFACT インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="49667-116">This Error/Warning/Information event indicates that the EDI receive pipeline could not process the incoming EDIFACT interchange because the characters used in the interchange did not conform to the character set identified in field UNB1.1 of the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="49667-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="49667-117">User Action</span></span>  
 <span data-ttu-id="49667-118">このエラーを解決するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="49667-118">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="49667-119">インターチェンジで使用されている文字を、インターチェンジの UNB1.1 で指定されている文字セットに一致するように変更します。</span><span class="sxs-lookup"><span data-stu-id="49667-119">Change the characters used in the interchange so they conform to the character set specified in field UNB1.1 of the interchange.</span></span>  
  
-   <span data-ttu-id="49667-120">インターチェンジの UNB1.1 フィールドに指定されている文字セットを変更し、インターチェンジのすべての文字がその文字セットに属する文字になるようにします。</span><span class="sxs-lookup"><span data-stu-id="49667-120">Change the character set specified in field UNB1.1 of the interchange, so all characters in the interchange are part of the character set.</span></span>