---
title: "手順 2: サーバー上の NLB の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Network Load Balancing
- configuring, NLB
- NLB
ms.assetid: 30b2f645-b495-49a5-852b-cf89d25fd2b7
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f10a05f23012990a1a0cc3dd50e0ca3db4282c84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-configuring-nlb-on-the-servers"></a><span data-ttu-id="156ac-102">手順 2: サーバーで NLB を構成します。</span><span class="sxs-lookup"><span data-stu-id="156ac-102">Step 2: Configuring NLB on the Servers</span></span>
<span data-ttu-id="156ac-103">リストにログインをベース プラットフォームをインストールして、適切なネットワークの設定で、サーバーを構成した後 (を参照してください[手順 1: 基本プラットフォームをインストールする](../../adapters-and-accelerators/accelerator-swift/step-1-installing-the-base-platform.md))、BizTalk HTTP フロント エンド サーバーと、BizTalk で負荷分散を有効にする必要がありますメッセージング サーバー。</span><span class="sxs-lookup"><span data-stu-id="156ac-103">After you have installed the base platform and configured the servers with the proper network settings (see [Step 1: Installing the Base Platform](../../adapters-and-accelerators/accelerator-swift/step-1-installing-the-base-platform.md)), you may need to enable load balancing on BizTalk HTTP front-end servers and the BizTalk Messaging servers.</span></span> <span data-ttu-id="156ac-104">1 つまたは複数 BizTalk HTTP フロント エンド サーバー 1 台以上の BizTalk メッセージのサーバーから別のコンピューターにインストールされている場合にのみ、この手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="156ac-104">This step is needed only if you have one or more BizTalk HTTP front-end servers installed on a separate computer from one or more BizTalk Messaging servers.</span></span>  
  
 <span data-ttu-id="156ac-105">クライアント コンピューター (Internet Explorer のユーザーが MRSR サイトを参照) と MRSR サーバー間および MRSR サーバーおよびメッセージング サーバーとの間の高可用性通信を保証する負荷分散します。</span><span class="sxs-lookup"><span data-stu-id="156ac-105">Load balancing ensures high-availability communication between the client computers (Internet Explorer users browsing to the MRSR site) and the MRSR servers, and between the MRSR servers and the messaging servers.</span></span>  
  
 <span data-ttu-id="156ac-106">負荷分散、**パブリック**イントラネット ユーザーがこれらのコンピューター上の IIS Web サーバーに接続できるようにする HTTP フロント エンド サーバーのインターフェイスが必要です。</span><span class="sxs-lookup"><span data-stu-id="156ac-106">Load balancing on the **Public** interfaces of the HTTP front-end servers is required to enable the Intranet users to connect to the IIS Web servers on these computers.</span></span> <span data-ttu-id="156ac-107">負荷分散、**プライベート**メッセージング サーバーがこれらのコンピューターで web サービスにお問い合わせを有効にする HTTP フロント エンド サーバーのインターフェイスが必要です。</span><span class="sxs-lookup"><span data-stu-id="156ac-107">Load balancing on the **Private** interfaces of the HTTP front-end servers is required to enable the messaging servers to contact the web services on these computers.</span></span>  
  
 <span data-ttu-id="156ac-108">メッセージングのサーバーで次の 2 つのサーバーがあると仮定すると負荷分散の構成で、**プライベート**ネットワーク アダプター。</span><span class="sxs-lookup"><span data-stu-id="156ac-108">On the messaging servers, assuming there are two servers, configure load balancing on the **Private** network adapters.</span></span>  
  
 <span data-ttu-id="156ac-109">詳細については、次を参照してください。、[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]デプロイメント ガイド 』。</span><span class="sxs-lookup"><span data-stu-id="156ac-109">For more information, see the [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Deployment Guide.</span></span>