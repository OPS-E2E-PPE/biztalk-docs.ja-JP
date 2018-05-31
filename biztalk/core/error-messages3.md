---
title: エラー Messages3 |Microsoft ドキュメント
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
ms.openlocfilehash: 2f1b9dd41280593de1472cd6af57ae8d1eb9fc58
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241778"
---
# <a name="error-messages"></a><span data-ttu-id="11b04-102">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="11b04-102">Error Messages</span></span>
<span data-ttu-id="11b04-103">次の表は、PeopleSoft Enterprise システムのコンポーネント インターフェイスのエラー メッセージ、各メッセージの説明、および考えられる修正方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="11b04-103">The following table lists error messages in the PeopleSoft Enterprise system's component interfaces, their descriptions, and possible corrections.</span></span>  
  
 <span data-ttu-id="11b04-104">**エラー メッセージ**</span><span class="sxs-lookup"><span data-stu-id="11b04-104">**Error messages**</span></span>  
  
|<span data-ttu-id="11b04-105">エラー ID</span><span class="sxs-lookup"><span data-stu-id="11b04-105">Error ID</span></span>|<span data-ttu-id="11b04-106">考えられる原因/エラーの説明</span><span class="sxs-lookup"><span data-stu-id="11b04-106">Possible Cause / Error Description</span></span>|<span data-ttu-id="11b04-107">考えられる修正</span><span class="sxs-lookup"><span data-stu-id="11b04-107">Possible Correction</span></span>|  
|--------------|-----------------------------------------|-------------------------|  
|<span data-ttu-id="11b04-108">E-JNI0004</span><span class="sxs-lookup"><span data-stu-id="11b04-108">E-JNI0004</span></span>|<span data-ttu-id="11b04-109">psjoa.jar がありません。</span><span class="sxs-lookup"><span data-stu-id="11b04-109">No psjoa.jar.</span></span><br /><br /> <span data-ttu-id="11b04-110">Java 例外が発生しました。</span><span class="sxs-lookup"><span data-stu-id="11b04-110">A Java exception occurred.</span></span>|<span data-ttu-id="11b04-111">PeopleSoft psjoa.jar ファイルの場所を確認してください。</span><span class="sxs-lookup"><span data-stu-id="11b04-111">Verify location of the PeopleSoft psjoa.jar file.</span></span>|  
|<span data-ttu-id="11b04-112">E-PSFT0030</span><span class="sxs-lookup"><span data-stu-id="11b04-112">E-PSFT0030</span></span>|<span data-ttu-id="11b04-113">psjoa.jar がありません。</span><span class="sxs-lookup"><span data-stu-id="11b04-113">No psjoa.jar.</span></span><br /><br /> <span data-ttu-id="11b04-114">コンポーネント インターフェイス Bean のインスタンスを作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="11b04-114">Failed to instantiate Component Interface Beans.</span></span>|<span data-ttu-id="11b04-115">PeopleSoft psjoa.jar ファイルの場所を確認してください。</span><span class="sxs-lookup"><span data-stu-id="11b04-115">Verify location of the PeopleSoft psjoa.jar file.</span></span>|  
|<span data-ttu-id="11b04-116">E-PSFT0019</span><span class="sxs-lookup"><span data-stu-id="11b04-116">E-PSFT0019</span></span>|<span data-ttu-id="11b04-117">サーバー名が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="11b04-117">Wrong server name.</span></span><br /><br /> <span data-ttu-id="11b04-118">PeopleSoft Application Server への接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="11b04-118">Connection to PeopleSoft Application Server failed.</span></span>|<span data-ttu-id="11b04-119">PeopleSoft ホスト パラメーターとユーザー パラメーターを確認してください。</span><span class="sxs-lookup"><span data-stu-id="11b04-119">Verify PeopleSoft host and user parameters.</span></span>|  
|<span data-ttu-id="11b04-120">E-PSFT0024</span><span class="sxs-lookup"><span data-stu-id="11b04-120">E-PSFT0024</span></span>|<span data-ttu-id="11b04-121">ユーザー名とパスワードが正しくありません。</span><span class="sxs-lookup"><span data-stu-id="11b04-121">Wrong user name and password.</span></span><br /><br /> <span data-ttu-id="11b04-122">接続に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="11b04-122">Connection failed.</span></span> <span data-ttu-id="11b04-123">エラー メッセージ: は JavaClient は無効なユーザー名、または誤ったパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="11b04-123">Error Message: JavaClient is an Invalid User name, or you typed the wrong password.</span></span>|<span data-ttu-id="11b04-124">PeopleSoft のユーザー名とパスワードは必須であり、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="11b04-124">PeopleSoft user name and password are required and are case sensitive.</span></span> <span data-ttu-id="11b04-125">入力した情報の大文字と小文字の区別が正しいことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="11b04-125">Make sure that you are entering the information in the correct upper and lower cases.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="11b04-126">参照</span><span class="sxs-lookup"><span data-stu-id="11b04-126">See Also</span></span>  
 [<span data-ttu-id="11b04-127">PeopleSoft のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="11b04-127">Troubleshooting PeopleSoft</span></span>](../core/troubleshooting-peoplesoft.md)