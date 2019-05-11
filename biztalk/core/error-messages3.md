---
title: エラー Messages3 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- error messages
ms.assetid: 10ea12bb-eacb-477a-bc88-28f999e60a02
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 789bd5cdd12d14727320e50e6c8f9bc28f721333
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347357"
---
# <a name="error-messages"></a><span data-ttu-id="4dfa0-102">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="4dfa0-102">Error Messages</span></span>
<span data-ttu-id="4dfa0-103">次の表では、エラー メッセージで、PeopleSoft Enterprise システムのコンポーネント インターフェイスとその説明、および考えられる修正方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4dfa0-103">The following table lists error messages in the PeopleSoft Enterprise system's component interfaces, their descriptions, and possible corrections.</span></span>  
  
 <span data-ttu-id="4dfa0-104">**エラー メッセージ**</span><span class="sxs-lookup"><span data-stu-id="4dfa0-104">**Error messages**</span></span>  
  
|<span data-ttu-id="4dfa0-105">エラー ID</span><span class="sxs-lookup"><span data-stu-id="4dfa0-105">Error ID</span></span>|<span data-ttu-id="4dfa0-106">考えられる原因/エラーの説明</span><span class="sxs-lookup"><span data-stu-id="4dfa0-106">Possible Cause / Error Description</span></span>|<span data-ttu-id="4dfa0-107">考えられる修正</span><span class="sxs-lookup"><span data-stu-id="4dfa0-107">Possible Correction</span></span>|  
|--------------|-----------------------------------------|-------------------------|  
|<span data-ttu-id="4dfa0-108">E-JNI0004</span><span class="sxs-lookup"><span data-stu-id="4dfa0-108">E-JNI0004</span></span>|<span data-ttu-id="4dfa0-109">Psjoa.jar がありません。</span><span class="sxs-lookup"><span data-stu-id="4dfa0-109">No psjoa.jar.</span></span><br /><br /> <span data-ttu-id="4dfa0-110">Java 例外が発生しました。</span><span class="sxs-lookup"><span data-stu-id="4dfa0-110">A Java exception occurred.</span></span>|<span data-ttu-id="4dfa0-111">PeopleSoft psjoa.jar ファイルの場所を確認します。</span><span class="sxs-lookup"><span data-stu-id="4dfa0-111">Verify location of the PeopleSoft psjoa.jar file.</span></span>|  
|<span data-ttu-id="4dfa0-112">E-PSFT0030</span><span class="sxs-lookup"><span data-stu-id="4dfa0-112">E-PSFT0030</span></span>|<span data-ttu-id="4dfa0-113">Psjoa.jar がありません。</span><span class="sxs-lookup"><span data-stu-id="4dfa0-113">No psjoa.jar.</span></span><br /><br /> <span data-ttu-id="4dfa0-114">コンポーネント インターフェイス Bean のインスタンスを作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="4dfa0-114">Failed to instantiate Component Interface Beans.</span></span>|<span data-ttu-id="4dfa0-115">PeopleSoft psjoa.jar ファイルの場所を確認します。</span><span class="sxs-lookup"><span data-stu-id="4dfa0-115">Verify location of the PeopleSoft psjoa.jar file.</span></span>|  
|<span data-ttu-id="4dfa0-116">E-PSFT0019</span><span class="sxs-lookup"><span data-stu-id="4dfa0-116">E-PSFT0019</span></span>|<span data-ttu-id="4dfa0-117">間違ったサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="4dfa0-117">Wrong server name.</span></span><br /><br /> <span data-ttu-id="4dfa0-118">PeopleSoft Application Server への接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="4dfa0-118">Connection to PeopleSoft Application Server failed.</span></span>|<span data-ttu-id="4dfa0-119">PeopleSoft ホストとユーザーのパラメーターを確認します。</span><span class="sxs-lookup"><span data-stu-id="4dfa0-119">Verify PeopleSoft host and user parameters.</span></span>|  
|<span data-ttu-id="4dfa0-120">E-PSFT0024</span><span class="sxs-lookup"><span data-stu-id="4dfa0-120">E-PSFT0024</span></span>|<span data-ttu-id="4dfa0-121">間違ったユーザー名とパスワード。</span><span class="sxs-lookup"><span data-stu-id="4dfa0-121">Wrong user name and password.</span></span><br /><br /> <span data-ttu-id="4dfa0-122">接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="4dfa0-122">Connection failed.</span></span> <span data-ttu-id="4dfa0-123">エラー メッセージ:JavaClient は無効なユーザー名の場合、または誤ったパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="4dfa0-123">Error Message: JavaClient is an Invalid User name, or you typed the wrong password.</span></span>|<span data-ttu-id="4dfa0-124">PeopleSoft のユーザー名とパスワードに必要なし、小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="4dfa0-124">PeopleSoft user name and password are required and are case sensitive.</span></span> <span data-ttu-id="4dfa0-125">適切な大文字と小文字の情報を入力することを確認します。</span><span class="sxs-lookup"><span data-stu-id="4dfa0-125">Make sure that you are entering the information in the correct upper and lower cases.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4dfa0-126">参照</span><span class="sxs-lookup"><span data-stu-id="4dfa0-126">See Also</span></span>  
 [<span data-ttu-id="4dfa0-127">PeopleSoft のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="4dfa0-127">Troubleshooting PeopleSoft</span></span>](../core/troubleshooting-peoplesoft.md)