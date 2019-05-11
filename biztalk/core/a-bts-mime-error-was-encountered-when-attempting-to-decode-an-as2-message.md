---
title: AS2 メッセージをデコードしようとしていますときに BTS MIME エラーが発生しました |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65cb5ece-78e4-4b83-b126-4d8c588b2c61
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 411359b55fff0385cdda5ae52a9c59477526ccb3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362458"
---
# <a name="a-bts-mime-error-was-encountered-when-attempting-to-decode-an-as2-message"></a><span data-ttu-id="21e72-102">AS2 メッセージをデコードしようとしています。 ときに BTS MIME エラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="21e72-102">A BTS MIME error was encountered when attempting to decode an AS2 message</span></span>
## <a name="details"></a><span data-ttu-id="21e72-103">詳細</span><span class="sxs-lookup"><span data-stu-id="21e72-103">Details</span></span>  
  
|                 |                                                                                                                                    |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="21e72-104">製品名</span><span class="sxs-lookup"><span data-stu-id="21e72-104">Product Name</span></span>   |                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                         |
| <span data-ttu-id="21e72-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="21e72-105">Product Version</span></span> |                                     [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                     |
|    <span data-ttu-id="21e72-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="21e72-106">Event ID</span></span>     |                                                                 -                                                                  |
|  <span data-ttu-id="21e72-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="21e72-107">Event Source</span></span>   |                                                         <span data-ttu-id="21e72-108">BizTalk Server EDI</span><span class="sxs-lookup"><span data-stu-id="21e72-108">BizTalk Server EDI</span></span>                                                         |
|    <span data-ttu-id="21e72-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="21e72-109">Component</span></span>    |                                                             <span data-ttu-id="21e72-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="21e72-110">AS2 Engine</span></span>                                                             |
|  <span data-ttu-id="21e72-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="21e72-111">Symbolic Name</span></span>  |                                                                 -                                                                  |
|  <span data-ttu-id="21e72-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="21e72-112">Message Text</span></span>   | <span data-ttu-id="21e72-113">AS2 メッセージをデコードしようとしています。 BTS MIME エラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="21e72-113">A BTS MIME error was encountered when attempting to decode an AS2 message.</span></span>  <span data-ttu-id="21e72-114">AS2-から: {0}、AS2-を: {1}、MessageId:{2}エラー。 {3}</span><span class="sxs-lookup"><span data-stu-id="21e72-114">AS2-From: {0}, AS2-To: {1}, MessageId: {2}, Error: {3}</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="21e72-115">説明</span><span class="sxs-lookup"><span data-stu-id="21e72-115">Explanation</span></span>  
 <span data-ttu-id="21e72-116">BizTalk MIME コンポーネントを使用して、MIME 処理の一部を処理する場合は、このエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="21e72-116">This error is encountered when using the BizTalk MIME component to handle part of the MIME processing.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="21e72-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="21e72-117">User Action</span></span>  
 <span data-ttu-id="21e72-118">完全なエラー メッセージでは、MIME コンポーネントで発生した問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="21e72-118">The full error message provides the information about the problem encountered by the MIME component.</span></span> <span data-ttu-id="21e72-119">(これは、AS2 コンポーネントは MIME 処理の一部の BizTalk MIME コンポーネントを使用するため)、問題の診断の BTS MIME エラー情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21e72-119">Refer to the BTS MIME error information for diagnosis of the problem (this is because the AS2 components use the BizTalk MIME components for part of the MIME processing).</span></span>