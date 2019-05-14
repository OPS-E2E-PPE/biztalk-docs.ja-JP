---
title: 手順 2:サーバーに NLB を構成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Network Load Balancing
- configuring, NLB
- NLB
ms.assetid: 30b2f645-b495-49a5-852b-cf89d25fd2b7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad409c9a4287cee985d0a7f270370b97d5d8cf4b
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530013"
---
# <a name="step-2-configuring-nlb-on-the-servers"></a><span data-ttu-id="1993e-102">手順 2:サーバーに NLB を構成します。</span><span class="sxs-lookup"><span data-stu-id="1993e-102">Step 2: Configuring NLB on the Servers</span></span>
<span data-ttu-id="1993e-103">基本プラットフォームをインストールして適切なネットワークの設定でサーバーを構成した後 (を参照してください[手順 1。基本プラットフォームのインストール](../../adapters-and-accelerators/accelerator-swift/step-1-installing-the-base-platform.md))、BizTalk HTTP フロント エンド サーバーと BizTalk メッセージング サーバーでの負荷分散を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1993e-103">After you have installed the base platform and configured the servers with the proper network settings (see [Step 1: Installing the Base Platform](../../adapters-and-accelerators/accelerator-swift/step-1-installing-the-base-platform.md)), you may need to enable load balancing on BizTalk HTTP front-end servers and the BizTalk Messaging servers.</span></span> <span data-ttu-id="1993e-104">この手順は、1 つまたは複数 BizTalk HTTP フロント エンド サーバーがある 1 つまたは複数の BizTalk メッセージング サーバーから別のコンピューターにインストールされている場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="1993e-104">This step is needed only if you have one or more BizTalk HTTP front-end servers installed on a separate computer from one or more BizTalk Messaging servers.</span></span>  
  
 <span data-ttu-id="1993e-105">負荷分散により、高可用性の通信、クライアント コンピューター (Internet Explorer のユーザーが MRSR サイトを参照) と、MRSR サーバー間および MRSR サーバーと、メッセージング サーバーです。</span><span class="sxs-lookup"><span data-stu-id="1993e-105">Load balancing ensures high-availability communication between the client computers (Internet Explorer users browsing to the MRSR site) and the MRSR servers, and between the MRSR servers and the messaging servers.</span></span>  
  
 <span data-ttu-id="1993e-106">負荷分散、**パブリック**イントラネット ユーザーは、これらのコンピューター上の IIS Web サーバーに接続を有効に HTTP フロント エンド サーバーのインターフェイスが必要です。</span><span class="sxs-lookup"><span data-stu-id="1993e-106">Load balancing on the **Public** interfaces of the HTTP front-end servers is required to enable the Intranet users to connect to the IIS Web servers on these computers.</span></span> <span data-ttu-id="1993e-107">負荷分散、**プライベート**これらのコンピューター上の web サービスにお問い合わせくださいメッセージング サーバーを有効に HTTP フロント エンド サーバーのインターフェイスが必要です。</span><span class="sxs-lookup"><span data-stu-id="1993e-107">Load balancing on the **Private** interfaces of the HTTP front-end servers is required to enable the messaging servers to contact the web services on these computers.</span></span>  
  
 <span data-ttu-id="1993e-108">メッセージング サーバーに 2 つのサーバーがあると仮定すると構成の負荷分散、**プライベート**ネットワーク アダプター。</span><span class="sxs-lookup"><span data-stu-id="1993e-108">On the messaging servers, assuming there are two servers, configure load balancing on the **Private** network adapters.</span></span>  
  
 <span data-ttu-id="1993e-109">詳細については、BizTalk Server の展開ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1993e-109">For more information, see the BizTalk Server Deployment Guide.</span></span>