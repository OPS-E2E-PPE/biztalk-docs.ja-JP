---
title: シングル サインオン:イベント 10564 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e523c97a-608e-4bf4-8747-cfa0cce10acf
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ddea5def52677643930d215bd17a82359b55d90
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398799"
---
# <a name="single-sign-on-event-10564"></a><span data-ttu-id="15c1d-102">シングル サインオン:イベント 10564</span><span class="sxs-lookup"><span data-stu-id="15c1d-102">Single Sign-On: Event 10564</span></span>
## <a name="details"></a><span data-ttu-id="15c1d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="15c1d-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="15c1d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="15c1d-104">Product Name</span></span>   |                 <span data-ttu-id="15c1d-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="15c1d-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="15c1d-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="15c1d-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="15c1d-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="15c1d-107">Event ID</span></span>     |                           <span data-ttu-id="15c1d-108">10564</span><span class="sxs-lookup"><span data-stu-id="15c1d-108">10564</span></span>                            |
|  <span data-ttu-id="15c1d-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="15c1d-109">Event Source</span></span>   |                           <span data-ttu-id="15c1d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="15c1d-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="15c1d-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="15c1d-111">Component</span></span>    |                            <span data-ttu-id="15c1d-112">なし</span><span class="sxs-lookup"><span data-stu-id="15c1d-112">N/A</span></span>                             |
|  <span data-ttu-id="15c1d-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="15c1d-113">Symbolic Name</span></span>  |           <span data-ttu-id="15c1d-114">SSO_ERROR_BACKUP_FILE_INCORRECT_FORMAT</span><span class="sxs-lookup"><span data-stu-id="15c1d-114">SSO_ERROR_BACKUP_FILE_INCORRECT_FORMAT</span></span>           |
|  <span data-ttu-id="15c1d-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="15c1d-115">Message Text</span></span>   |     <span data-ttu-id="15c1d-116">バックアップ ファイルには、正しい形式はありません。</span><span class="sxs-lookup"><span data-stu-id="15c1d-116">The backup file does not have the correct format.</span></span>      |
  
## <a name="explanation"></a><span data-ttu-id="15c1d-117">説明</span><span class="sxs-lookup"><span data-stu-id="15c1d-117">Explanation</span></span>  
 <span data-ttu-id="15c1d-118">バックアップ ファイルには、正しい形式はありません。</span><span class="sxs-lookup"><span data-stu-id="15c1d-118">The backup file does not have the correct format.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="15c1d-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="15c1d-119">User Action</span></span>  
 <span data-ttu-id="15c1d-120">正しいファイル名と場所があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="15c1d-120">Check that you have the correct file and location.</span></span> <span data-ttu-id="15c1d-121">そのフォルダー内の他のファイルがないことを確認する必要がありますもします。BAK の拡張機能は、ENTSSO システムとして可能性がありますと混同する実際のバックアップ ファイル。</span><span class="sxs-lookup"><span data-stu-id="15c1d-121">You should also confirm that there are no other files in that folder with the .BAK extension, as the ENTSSO system may confuse them with the actual backup file.</span></span>