---
title: PeopleSoft トランスポートのプロパティ ダイアログ ボックス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- PeopleSoft
helpviewer_keywords:
- PeopleSoft Transport Properties dialog box
ms.assetid: 660f0a0b-e076-4f4e-8b2a-6d976acfc5ce
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8134f51cd6ac0ef90b2ef204b4e6c6ee38f7b6b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65322169"
---
# <a name="peoplesoft-transport-properties-dialog-box"></a><span data-ttu-id="61342-102">PeopleSoft トランスポートのプロパティ ダイアログ ボックス</span><span class="sxs-lookup"><span data-stu-id="61342-102">PeopleSoft Transport Properties Dialog Box</span></span>
<span data-ttu-id="61342-103">PeopleSoft トランスポートのプロパティ ダイアログ ボックスを使用して、アダプターに必要なプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="61342-103">Use the PeopleSoft Transport Properties dialog box to set the adapter-required properties.</span></span>  
  
|<span data-ttu-id="61342-104">プロパティ</span><span class="sxs-lookup"><span data-stu-id="61342-104">Use this</span></span>|<span data-ttu-id="61342-105">目的</span><span class="sxs-lookup"><span data-stu-id="61342-105">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="61342-106">**アダプタに必要なプロパティ**</span><span class="sxs-lookup"><span data-stu-id="61342-106">**Adapter Required Properties**</span></span>||  
|<span data-ttu-id="61342-107">アプリケーション サーバーのパス</span><span class="sxs-lookup"><span data-stu-id="61342-107">Application server path</span></span>|<span data-ttu-id="61342-108">PeopleSoft server のパスを入力 (たとえば、 `//psserver.domain.com:9000`)。</span><span class="sxs-lookup"><span data-stu-id="61342-108">Type the path for the PeopleSoft server (for example, `//psserver.domain.com:9000`).</span></span>|  
|<span data-ttu-id="61342-109">JAVA_HOME</span><span class="sxs-lookup"><span data-stu-id="61342-109">JAVA_HOME</span></span>|<span data-ttu-id="61342-110">JAVA_HOME の場所の名前を入力 (たとえば、 `<drive:>\jdk1.4.2_08`)。</span><span class="sxs-lookup"><span data-stu-id="61342-110">Type the name for the JAVA_HOME location (for example, `<drive:>\jdk1.4.2_08`).</span></span>|  
|<span data-ttu-id="61342-111">パスワード</span><span class="sxs-lookup"><span data-stu-id="61342-111">Password</span></span>|<span data-ttu-id="61342-112">このユーザーのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="61342-112">Type the password for this user.</span></span>|  
|<span data-ttu-id="61342-113">PeopleSoft 8.x JAR ファイル</span><span class="sxs-lookup"><span data-stu-id="61342-113">PeopleSoft 8.x JAR files</span></span>|<span data-ttu-id="61342-114">PeopleSoft JAR ファイルの場所のパスを入力 (たとえば、 `<drive:>\JAR_FILES\Peoplesoft_8.4\psjoa.jar`)。</span><span class="sxs-lookup"><span data-stu-id="61342-114">Type the path for the location of the PeopleSoft JAR files (for example, `<drive:>\JAR_FILES\Peoplesoft_8.4\psjoa.jar`).</span></span>|  
|<span data-ttu-id="61342-115">[ユーザー名]</span><span class="sxs-lookup"><span data-stu-id="61342-115">User name</span></span>|<span data-ttu-id="61342-116">ユーザーの名前を入力し、をクリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="61342-116">Type the name of the user, and click **OK**.</span></span>|  
|<span data-ttu-id="61342-117">**追加のパラメーター**</span><span class="sxs-lookup"><span data-stu-id="61342-117">**Additional Parameters**</span></span>||  
|<span data-ttu-id="61342-118">データベースの日付形式</span><span class="sxs-lookup"><span data-stu-id="61342-118">Database Date Format</span></span>|<span data-ttu-id="61342-119">入力日付を表示する形式 (たとえば、**- YYYY-MM-DD**)。</span><span class="sxs-lookup"><span data-stu-id="61342-119">Type the format in which you want dates to appear (for example,**YYYY-MM-DD**).</span></span><br /><br /> <span data-ttu-id="61342-120">日付には、キーとして使用する場合に、さまざまな形式があります。</span><span class="sxs-lookup"><span data-stu-id="61342-120">The date has a different format when used as a key.</span></span>|  
|<span data-ttu-id="61342-121">**同時実行制御**</span><span class="sxs-lookup"><span data-stu-id="61342-121">**Concurrency Control**</span></span>||  
|<span data-ttu-id="61342-122">最大同時呼び出し数</span><span class="sxs-lookup"><span data-stu-id="61342-122">Max Concurrent Calls</span></span>|<span data-ttu-id="61342-123">数値を入力、**最大同時呼び出し数**します。</span><span class="sxs-lookup"><span data-stu-id="61342-123">Type a numeric value for the **Max Concurrent Calls**.</span></span> <span data-ttu-id="61342-124">この数は、たとえば、200 の同時呼び出しの最大数を表します。</span><span class="sxs-lookup"><span data-stu-id="61342-124">This number represents the maximum number of concurrent calls, for example, 200.</span></span><br /><br /> <span data-ttu-id="61342-125">既定値のこのフィールドが-1 の場合に発生します保護れないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="61342-125">The default value for this field is -1, meaning no protection occurs.</span></span>|  
|<span data-ttu-id="61342-126">**Connection**</span><span class="sxs-lookup"><span data-stu-id="61342-126">**Connection**</span></span>||  
|<span data-ttu-id="61342-127">セッションの最大数</span><span class="sxs-lookup"><span data-stu-id="61342-127">Maximum number of sessions</span></span>|<span data-ttu-id="61342-128">セッションの最大数を表す数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="61342-128">Type a number to represent the maximum number of sessions.</span></span><br /><br /> <span data-ttu-id="61342-129">既定の接続数には 40 です。</span><span class="sxs-lookup"><span data-stu-id="61342-129">The default number of connections is 40.</span></span>|  
|<span data-ttu-id="61342-130">**エージェントを更新します。**</span><span class="sxs-lookup"><span data-stu-id="61342-130">**Refresh Agent**</span></span>||  
|<span data-ttu-id="61342-131">エージェントの更新</span><span class="sxs-lookup"><span data-stu-id="61342-131">Refresh Agent</span></span>|<span data-ttu-id="61342-132">選択**はい**の**エージェントの更新**runtimeagent.exe および browsingagent.exe の処理を必要な場合に自動的に再起動を強制します。</span><span class="sxs-lookup"><span data-stu-id="61342-132">Select **Yes** for the **Refresh Agent** to force the runtimeagent.exe and the browsingagent.exe processes to restart automatically when required.</span></span><br /><br /> <span data-ttu-id="61342-133">など、処理をサーバーとの接続が失われた場合、またはサーバーに追加して、アダプター ウィザードで選択範囲のない場合、自動的に再起動が必要です。</span><span class="sxs-lookup"><span data-stu-id="61342-133">For example, you want the process to restart automatically if it loses connection with the server, or if you add something to the server and it does not appear in the Adapter Wizard for selection.</span></span>|  
|<span data-ttu-id="61342-134">**シングル サインオン**</span><span class="sxs-lookup"><span data-stu-id="61342-134">**Single Sign-On**</span></span>||  
|<span data-ttu-id="61342-135">[関連アプリケーション]</span><span class="sxs-lookup"><span data-stu-id="61342-135">Affiliate Application</span></span>|<span data-ttu-id="61342-136">シングル サインオン (SSO) を使用している場合にのみ、一覧から関連アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="61342-136">Select the affiliate application from the list only if you are using Single Sign-ON (SSO).</span></span>|  
|<span data-ttu-id="61342-137">SSO の使用</span><span class="sxs-lookup"><span data-stu-id="61342-137">Use SSO</span></span>|<span data-ttu-id="61342-138">選択**はい**SSO; を使用している場合、パスワードは必要ありませんここでします。</span><span class="sxs-lookup"><span data-stu-id="61342-138">Select **Yes** if you are using SSO; a password is not required in this case.</span></span> <span data-ttu-id="61342-139">**注:** 既にパスワードを入力したシングル サインオンを使用する場合は、パスワード フィールドと選択を右クリックして**パスワードの無効化**します。</span><span class="sxs-lookup"><span data-stu-id="61342-139">**Note:**  If you already entered a password and you want to use Single Sign-On, right-click the Password field and select **Nullify Password**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="61342-140">参照</span><span class="sxs-lookup"><span data-stu-id="61342-140">See Also</span></span>  
 [<span data-ttu-id="61342-141">BizTalk Adapter for PeopleSoft Enterprise の UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="61342-141">UI Reference for BizTalk Adapter for PeopleSoft Enterprise</span></span>](../core/ui-reference-for-biztalk-adapter-for-peoplesoft-enterprise.md)