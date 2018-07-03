---
title: 'シングル サインオン: イベント 10564 |Microsoft Docs'
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
ms.openlocfilehash: 8be4ea87757a1fa0cb5d8ebd2e344ce521dbf740
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997147"
---
# <a name="single-sign-on-event-10564"></a><span data-ttu-id="891b6-102">シングル サインオン: イベント 10564</span><span class="sxs-lookup"><span data-stu-id="891b6-102">Single Sign-On: Event 10564</span></span>
## <a name="details"></a><span data-ttu-id="891b6-103">詳細</span><span class="sxs-lookup"><span data-stu-id="891b6-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="891b6-104">製品名</span><span class="sxs-lookup"><span data-stu-id="891b6-104">Product Name</span></span>   |                 <span data-ttu-id="891b6-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="891b6-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="891b6-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="891b6-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="891b6-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="891b6-107">Event ID</span></span>     |                           <span data-ttu-id="891b6-108">10564</span><span class="sxs-lookup"><span data-stu-id="891b6-108">10564</span></span>                            |
|  <span data-ttu-id="891b6-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="891b6-109">Event Source</span></span>   |                           <span data-ttu-id="891b6-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="891b6-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="891b6-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="891b6-111">Component</span></span>    |                            <span data-ttu-id="891b6-112">なし</span><span class="sxs-lookup"><span data-stu-id="891b6-112">N/A</span></span>                             |
|  <span data-ttu-id="891b6-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="891b6-113">Symbolic Name</span></span>  |           <span data-ttu-id="891b6-114">SSO_ERROR_BACKUP_FILE_INCORRECT_FORMAT</span><span class="sxs-lookup"><span data-stu-id="891b6-114">SSO_ERROR_BACKUP_FILE_INCORRECT_FORMAT</span></span>           |
|  <span data-ttu-id="891b6-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="891b6-115">Message Text</span></span>   |     <span data-ttu-id="891b6-116">バックアップ ファイルの形式が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="891b6-116">The backup file does not have the correct format.</span></span>      |
  
## <a name="explanation"></a><span data-ttu-id="891b6-117">説明</span><span class="sxs-lookup"><span data-stu-id="891b6-117">Explanation</span></span>  
 <span data-ttu-id="891b6-118">バックアップ ファイルの形式が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="891b6-118">The backup file does not have the correct format.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="891b6-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="891b6-119">User Action</span></span>  
 <span data-ttu-id="891b6-120">ファイルと場所が正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="891b6-120">Check that you have the correct file and location.</span></span> <span data-ttu-id="891b6-121">また、そのフォルダーに .BAK という拡張子のファイルが他にないことも確認する必要があります。ENTSSO システムが実際のバックアップ ファイルと混同する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="891b6-121">You should also confirm that there are no other files in that folder with the .BAK extension, as the ENTSSO system may confuse them with the actual backup file.</span></span>