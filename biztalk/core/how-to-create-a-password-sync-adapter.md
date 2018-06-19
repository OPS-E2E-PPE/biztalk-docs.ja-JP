---
title: パスワード同期アダプターを作成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: c47381cc1ed71788673602c1db7eec5b5ac049ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249370"
---
# <a name="how-to-create-a-password-sync-adapter"></a><span data-ttu-id="d56fe-102">パスワード同期アダプターを作成する方法</span><span class="sxs-lookup"><span data-stu-id="d56fe-102">How to Create a Password Sync Adapter</span></span>
<span data-ttu-id="d56fe-103">PS (パスワード同期) アダプターは、パスワード同期ヘルパー コンポーネントを使用して、エンタープライズ シングル サインオン (SSO) との間で通知を渡したり、受け取ったりするアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="d56fe-103">A password sync (PS) adapter is an application that uses the Password Sync Helper component to pass notifications to and from Enterprise Single Sign-On (SSO).</span></span> <span data-ttu-id="d56fe-104">PS ヘルパー コンポーネントは、COM および .NET フレームワーク インターフェイスを公開しますが、アダプターが COM コンポーネントである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d56fe-104">Note that although the PS Helper component exposes a COM and a .NET Framework interface, your adapter does not necessarily have to be a COM component.</span></span> <span data-ttu-id="d56fe-105">アダプターは、スタンドアロン プロセス、COM+ アプリケーション、または Windows サービスとしてデザインできます。</span><span class="sxs-lookup"><span data-stu-id="d56fe-105">You can design your adapter as a stand-alone process, a COM+ application, or a Windows service.</span></span>  
  
### <a name="to-create-a-password-sync-adapter"></a><span data-ttu-id="d56fe-106">パスワード同期アダプターを作成するには</span><span class="sxs-lookup"><span data-stu-id="d56fe-106">To create a password sync adapter</span></span>  
  
1.  <span data-ttu-id="d56fe-107">`ISSOPSWrapper.InitializeAdapter` を使用して、ENTSSO (エンタープライズ シングル サインオン) サービスに、プロバイダーがアクティブであることを通知します。</span><span class="sxs-lookup"><span data-stu-id="d56fe-107">Inform Enterprise Single Sign-On service (ENTSSO) that your provider is active using `ISSOPSWrapper.InitializeAdapter`.</span></span>  
  
     <span data-ttu-id="d56fe-108">`InitializeAdapter` は、プロバイダー (通常は呼び出しを実行するプロバイダーと同じ) が現在オンになっていて、システムのパスワードの更新のやり取りが可能であることを ENTSSO に通知します。</span><span class="sxs-lookup"><span data-stu-id="d56fe-108">`InitializeAdapter` informs ENTSSO that a provider, usually the same provider that is making the call, is currently turned on, and therefore will be communicating password updates to and from the system.</span></span> <span data-ttu-id="d56fe-109">また、`InitializeAdapter` を使用して、グループ アダプターなど、他のリソースをアクティブ化することもできます。</span><span class="sxs-lookup"><span data-stu-id="d56fe-109">You can also use `InitializeAdapter` to activate other resources such as group adapters.</span></span>  
  
2.  <span data-ttu-id="d56fe-110">`ISSOPSWrapper.SendNotification` を使用して、パスワードの更新を ENTSSO に送信します。</span><span class="sxs-lookup"><span data-stu-id="d56fe-110">Send password updates to ENTSSO by using `ISSOPSWrapper.SendNotification`.</span></span>  
  
     <span data-ttu-id="d56fe-111">Windows 以外のシステムからパスワードの更新を受け取る方法を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d56fe-111">You must determine how you receive password updates from your non-Windows system.</span></span> <span data-ttu-id="d56fe-112">更新を受け取った後で、`SendNotification` を使用してその情報を ENTSSO に渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="d56fe-112">After you receive the update, you can pass the information on to ENTSSO using `SendNotification`.</span></span> <span data-ttu-id="d56fe-113">なお`SendNotification`パスワードの更新を送信するだけではありません: のアーキテクチャ`SendNotification`他の種類の通知を送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="d56fe-113">Note that `SendNotification` is not limited to sending password updates: the architecture of `SendNotification` also enables you to send other types of notifications.</span></span>  
  
3.  <span data-ttu-id="d56fe-114">`ISSOPSWrapper.ReceiveNotification` を使用して、ENTSSO からのパスワードの更新を要求します。</span><span class="sxs-lookup"><span data-stu-id="d56fe-114">Request password updates from ENTSSO by using `ISSOPSWrapper.ReceiveNotification`.</span></span>  
  
     <span data-ttu-id="d56fe-115">パスワード同期アダプターはプル テクノロジであるため、ENTSSO はアダプターを呼び出しません。</span><span class="sxs-lookup"><span data-stu-id="d56fe-115">Because the password sync adapter is a pull technology, ENTSSO never calls your adapter.</span></span> <span data-ttu-id="d56fe-116">代わりに、アダプターは定期的に `ReceiveNotification` を呼び出して、パスワードの更新が利用可能であるかを確認します。</span><span class="sxs-lookup"><span data-stu-id="d56fe-116">Instead, your adapter periodically calls `ReceiveNotification` to see whether any password updates are available.</span></span> <span data-ttu-id="d56fe-117">WAIT フラグを `ReceiveNotification` に設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="d56fe-117">You can choose to set the WAIT flag on `ReceiveNotification`.</span></span> <span data-ttu-id="d56fe-118">WAIT を設定すると、通知が利用可能になるまでスレッドをブロックします。</span><span class="sxs-lookup"><span data-stu-id="d56fe-118">Setting WAIT blocks the thread until a notification is available.</span></span>  
  
     <span data-ttu-id="d56fe-119">ENTSSO がパスワードの変更をプレーン テキストでアダプターに配信することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d56fe-119">Note that ENTSSO delivers a password change to your adapter in plain text.</span></span> <span data-ttu-id="d56fe-120">パスワード情報が不正に漏えいされないように保護するのはアダプターの役割です。</span><span class="sxs-lookup"><span data-stu-id="d56fe-120">It is the responsibility of the adapter to protect that password information against incorrect disclosure.</span></span> <span data-ttu-id="d56fe-121">また、他の無効なソースからの偽装や攻撃 (パスワード同期ヘルパー コンポーネントの偽装など) からアダプター自身を保護することもアダプターの役割です。</span><span class="sxs-lookup"><span data-stu-id="d56fe-121">It is also the responsibility of the adapter to protect itself against spoofing or attacks from other invalid sources, including spoofing of the Password Sync Helper component.</span></span>  
  
     <span data-ttu-id="d56fe-122">`pReceiveNotification` パラメーターを使用して ENTSSO からパスワードの更新を受け取った後で、この情報を Windows 以外のシステムに渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="d56fe-122">After you receive a password update from ENTSSO through the `pReceiveNotification` parameter, you must pass this information on to your non-Windows system.</span></span> <span data-ttu-id="d56fe-123">`SendNotification` の場合と同じように、リモート サーバーと通信する最良の方法を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d56fe-123">As with `SendNotification`, you must determine the best way to communicate with the remote server.</span></span>  
  
4.  <span data-ttu-id="d56fe-124">`ISSOPSWrapper.ShutdownAdapter` を使用してアダプターをオフにします。</span><span class="sxs-lookup"><span data-stu-id="d56fe-124">Turn off your adapter using `ISSOPSWrapper.ShutdownAdapter`.</span></span>  
  
     <span data-ttu-id="d56fe-125">`ShutdownApplication` は、アダプターによって呼び出される最後のメソッドであり、アダプターが ENTSSO とのパスワードの更新のやり取りをそれ以上行わないことを示します。</span><span class="sxs-lookup"><span data-stu-id="d56fe-125">`ShutdownApplication` should be the last method called by an adapter, and indicates that the adapter will no longer send or receive password updates to ENTSSO.</span></span>  
  
     <span data-ttu-id="d56fe-126">アダプターがシャットダウンしている間、ENTSSO は、すべてのパスワードの変更をバッファー サイズいっぱいになるまで書き込みます。</span><span class="sxs-lookup"><span data-stu-id="d56fe-126">Note that ENTSSO buffers any password changes a user makes while the adapter is shut down, up to a buffer size limit.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d56fe-127">参照</span><span class="sxs-lookup"><span data-stu-id="d56fe-127">See Also</span></span>  
 <span data-ttu-id="d56fe-128">[エンタープライズ シングル サインオンを使用したプログラミング](../core/programming-with-enterprise-single-sign-on.md) </span><span class="sxs-lookup"><span data-stu-id="d56fe-128">[Programming with Enterprise Single Sign-On](../core/programming-with-enterprise-single-sign-on.md) </span></span>  
 [<span data-ttu-id="d56fe-129">パスワードの同期</span><span class="sxs-lookup"><span data-stu-id="d56fe-129">Synchronizing Passwords</span></span>](../core/synchronizing-passwords.md)