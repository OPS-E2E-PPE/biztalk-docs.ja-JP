---
title: パスワード同期アダプターを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: caa5bd13-efd9-4544-b5df-17d01c6ac5d8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2c3ca305f86f541bd1cb681ed97aea7768e77c7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65339930"
---
# <a name="how-to-create-a-password-sync-adapter"></a><span data-ttu-id="151c7-102">パスワード同期アダプターを作成する方法</span><span class="sxs-lookup"><span data-stu-id="151c7-102">How to Create a Password Sync Adapter</span></span>
<span data-ttu-id="151c7-103">パスワード同期 (PS) アダプターは、通知からエンタープライズ シングル サインオン (SSO) を渡すためのパスワード同期ヘルパー コンポーネントを使用するアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="151c7-103">A password sync (PS) adapter is an application that uses the Password Sync Helper component to pass notifications to and from Enterprise Single Sign-On (SSO).</span></span> <span data-ttu-id="151c7-104">PS ヘルパー コンポーネントは、COM および .NET Framework インターフェイスを公開する、アダプターとは限りませんが COM コンポーネントであるに注意してください。</span><span class="sxs-lookup"><span data-stu-id="151c7-104">Note that although the PS Helper component exposes a COM and a .NET Framework interface, your adapter does not necessarily have to be a COM component.</span></span> <span data-ttu-id="151c7-105">スタンドアロン プロセス、COM + アプリケーション、または Windows サービスとしてアダプターを設計することができます。</span><span class="sxs-lookup"><span data-stu-id="151c7-105">You can design your adapter as a stand-alone process, a COM+ application, or a Windows service.</span></span>  
  
### <a name="to-create-a-password-sync-adapter"></a><span data-ttu-id="151c7-106">パスワード同期アダプターを作成するには</span><span class="sxs-lookup"><span data-stu-id="151c7-106">To create a password sync adapter</span></span>  
  
1.  <span data-ttu-id="151c7-107">ご利用のプロバイダーは、active を使用して、エンタープライズ シングル サインオン サービス (ENTSSO) に通知`ISSOPSWrapper.InitializeAdapter`します。</span><span class="sxs-lookup"><span data-stu-id="151c7-107">Inform Enterprise Single Sign-On service (ENTSSO) that your provider is active using `ISSOPSWrapper.InitializeAdapter`.</span></span>  
  
     <span data-ttu-id="151c7-108">`InitializeAdapter` 呼び出しを行っている同じプロバイダーは、通常、プロバイダーは、オンになって現在は、して、システムとのパスワードの更新を通信するために ENTSSO を通知します。</span><span class="sxs-lookup"><span data-stu-id="151c7-108">`InitializeAdapter` informs ENTSSO that a provider, usually the same provider that is making the call, is currently turned on, and therefore will be communicating password updates to and from the system.</span></span> <span data-ttu-id="151c7-109">使用することも`InitializeAdapter`グループ アダプターなどの他のリソースをアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="151c7-109">You can also use `InitializeAdapter` to activate other resources such as group adapters.</span></span>  
  
2.  <span data-ttu-id="151c7-110">使用してパスワードの更新を ENTSSO に送信`ISSOPSWrapper.SendNotification`します。</span><span class="sxs-lookup"><span data-stu-id="151c7-110">Send password updates to ENTSSO by using `ISSOPSWrapper.SendNotification`.</span></span>  
  
     <span data-ttu-id="151c7-111">非 Windows システムからパスワードの更新を受け取る方法を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="151c7-111">You must determine how you receive password updates from your non-Windows system.</span></span> <span data-ttu-id="151c7-112">更新プログラムを受信した後は、ENTSSO を使用してログオン情報を渡すことができます`SendNotification`します。</span><span class="sxs-lookup"><span data-stu-id="151c7-112">After you receive the update, you can pass the information on to ENTSSO using `SendNotification`.</span></span> <span data-ttu-id="151c7-113">なお`SendNotification`パスワードの更新を送信するだけではありません: アーキテクチャの`SendNotification`他の種類の通知を送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="151c7-113">Note that `SendNotification` is not limited to sending password updates: the architecture of `SendNotification` also enables you to send other types of notifications.</span></span>  
  
3.  <span data-ttu-id="151c7-114">使用して ENTSSO からパスワードの更新を要求`ISSOPSWrapper.ReceiveNotification`します。</span><span class="sxs-lookup"><span data-stu-id="151c7-114">Request password updates from ENTSSO by using `ISSOPSWrapper.ReceiveNotification`.</span></span>  
  
     <span data-ttu-id="151c7-115">パスワード同期アダプターがプル テクノロジであるため、ENTSSO はアダプターを呼び出しません。</span><span class="sxs-lookup"><span data-stu-id="151c7-115">Because the password sync adapter is a pull technology, ENTSSO never calls your adapter.</span></span> <span data-ttu-id="151c7-116">アダプターが定期的に呼び出す代わりに、`ReceiveNotification`パスワードの更新が使用できるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="151c7-116">Instead, your adapter periodically calls `ReceiveNotification` to see whether any password updates are available.</span></span> <span data-ttu-id="151c7-117">WAIT フラグを設定することもできます`ReceiveNotification`します。</span><span class="sxs-lookup"><span data-stu-id="151c7-117">You can choose to set the WAIT flag on `ReceiveNotification`.</span></span> <span data-ttu-id="151c7-118">通知が利用可能になるまでスレッド待機ブロックを設定します。</span><span class="sxs-lookup"><span data-stu-id="151c7-118">Setting WAIT blocks the thread until a notification is available.</span></span>  
  
     <span data-ttu-id="151c7-119">ENTSSO がプレーン テキストでアダプターに、パスワードの変更を提供することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="151c7-119">Note that ENTSSO delivers a password change to your adapter in plain text.</span></span> <span data-ttu-id="151c7-120">そのパスワードの情報が不正に漏えいを保護するアダプターの役目です。</span><span class="sxs-lookup"><span data-stu-id="151c7-120">It is the responsibility of the adapter to protect that password information against incorrect disclosure.</span></span> <span data-ttu-id="151c7-121">スプーフィングから保護するアダプターの役割をもまたは、パスワード同期ヘルパー コンポーネントのスプーフィングを含む、他の無効なソースからの攻撃です。</span><span class="sxs-lookup"><span data-stu-id="151c7-121">It is also the responsibility of the adapter to protect itself against spoofing or attacks from other invalid sources, including spoofing of the Password Sync Helper component.</span></span>  
  
     <span data-ttu-id="151c7-122">使用して ENTSSO からパスワードの更新プログラムが表示されたら、`pReceiveNotification`パラメーター、非 Windows システムにこの情報を渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="151c7-122">After you receive a password update from ENTSSO through the `pReceiveNotification` parameter, you must pass this information on to your non-Windows system.</span></span> <span data-ttu-id="151c7-123">同様`SendNotification`、リモート サーバーと通信する最善の方法を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="151c7-123">As with `SendNotification`, you must determine the best way to communicate with the remote server.</span></span>  
  
4.  <span data-ttu-id="151c7-124">アダプターを使用して、オフにする`ISSOPSWrapper.ShutdownAdapter`します。</span><span class="sxs-lookup"><span data-stu-id="151c7-124">Turn off your adapter using `ISSOPSWrapper.ShutdownAdapter`.</span></span>  
  
     <span data-ttu-id="151c7-125">`ShutdownApplication` 必要があります、最後のメソッドは、アダプターによって呼び出され、アダプターが送信されなく、ENTSSO にパスワードの更新が表示されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="151c7-125">`ShutdownApplication` should be the last method called by an adapter, and indicates that the adapter will no longer send or receive password updates to ENTSSO.</span></span>  
  
     <span data-ttu-id="151c7-126">ENTSSO にアダプターがシャット ダウン中に、最大バッファー サイズの制限をユーザーが、パスワード変更がバッファーすることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="151c7-126">Note that ENTSSO buffers any password changes a user makes while the adapter is shut down, up to a buffer size limit.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="151c7-127">参照</span><span class="sxs-lookup"><span data-stu-id="151c7-127">See Also</span></span>  
 <span data-ttu-id="151c7-128">[エンタープライズ シングル サインオンを使用したプログラミング](../core/programming-with-enterprise-single-sign-on.md) </span><span class="sxs-lookup"><span data-stu-id="151c7-128">[Programming with Enterprise Single Sign-On](../core/programming-with-enterprise-single-sign-on.md) </span></span>  
 [<span data-ttu-id="151c7-129">パスワードの同期</span><span class="sxs-lookup"><span data-stu-id="151c7-129">Synchronizing Passwords</span></span>](../core/synchronizing-passwords.md)