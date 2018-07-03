---
title: CIDX サポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- CIDX, procedures
- CIDX, about CIDX
- CIDX, Elemica Exchange Server Provider (ESP)
- CIDX, PIPs
- CIDX
- Elemica Exchange Server Provider (ESP)
- procedures [CIDX]
- PIPs, CIDX
ms.assetid: 58b75ad3-f6b9-47c0-8dbf-506a3eaf010b
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57500dc25e719d7ef693975b74850cbc04289dec
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997811"
---
# <a name="cidx-support"></a><span data-ttu-id="bd2e7-102">CIDX サポート</span><span class="sxs-lookup"><span data-stu-id="bd2e7-102">CIDX Support</span></span>
<span data-ttu-id="bd2e7-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] CIDX (Chemical Industry Data Exchange) XML メッセージ交換のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="bd2e7-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] provides support for CIDX (Chemical Industry Data Exchange) XML message exchange.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="bd2e7-104"> CIDX Chem eStandards バージョン 2.0 および 3.0 では、RosettaNet 実装 Framework (RNIF) 1.1 を使用して、どちらもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="bd2e7-104"> supports CIDX Chem eStandards versions 2.0 and 3.0, both of which use the RosettaNet Implementation Framework (RNIF) 1.1.</span></span>  
  
 <span data-ttu-id="bd2e7-105">シングル アクションとダブル アクションのメッセージをサポートしている [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] の単純な非同期パブリック プロセスは、CIDX の Service Content を消費して、ルーティングします。</span><span class="sxs-lookup"><span data-stu-id="bd2e7-105">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] asynchronous simple public processes (supporting single-action and double-action messages) consume and route CIDX service content.</span></span>  
  
 <span data-ttu-id="bd2e7-106">CIDX PIP に基づくアグリーメントについて、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] ではメッセージ内の以下の要素を検証します。</span><span class="sxs-lookup"><span data-stu-id="bd2e7-106">For an agreement based on a CIDX PIP, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] will validate the following in a message:</span></span>  
  
- <span data-ttu-id="bd2e7-107">RNIF 1.1 バージョンのみ</span><span class="sxs-lookup"><span data-stu-id="bd2e7-107">RNIF 1.1 version only</span></span>  
  
- <span data-ttu-id="bd2e7-108">非 0A1</span><span class="sxs-lookup"><span data-stu-id="bd2e7-108">No 0A1</span></span>  
  
- <span data-ttu-id="bd2e7-109">シングル アクションのみ</span><span class="sxs-lookup"><span data-stu-id="bd2e7-109">Only Single Action</span></span>  
  
  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="bd2e7-110"> 設定から妨げません、 `Standard` "CIDX"に設定した後にプロセス構成のプロパティ、 `0A1 agreement` (は CIDX のサポートされていません)"0A1"には、そのプロファイルを使用して、アグリーメントのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="bd2e7-110"> will not prevent you from setting the `Standard` property for a process configuration to "CIDX", after you have set the `0A1 agreement` property for an agreement that uses that profile to "0A1" (which is not supported for CIDX).</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="bd2e7-111"> これを禁止するクロス フィールド検証は実行されません。</span><span class="sxs-lookup"><span data-stu-id="bd2e7-111"> does not perform the cross-field validation that would prevent this.</span></span>  
  
## <a name="applying-a-pip-to-a-cidx-implementation"></a><span data-ttu-id="bd2e7-112">PIP の CIDX 実装への適用</span><span class="sxs-lookup"><span data-stu-id="bd2e7-112">Applying a PIP to a CIDX Implementation</span></span>  
 <span data-ttu-id="bd2e7-113">PIP を CIDX 実装に適用するには、設定、`Standard`にプロセス構成プロファイルのプロパティ**CIDX**します。</span><span class="sxs-lookup"><span data-stu-id="bd2e7-113">To apply a PIP to a CIDX implementation, set the `Standard` property in the process configuration profile to **CIDX**.</span></span> <span data-ttu-id="bd2e7-114">メッセージ標準、標準のバージョン、およびペイロード バインド id。 の値を入力したらができます。</span><span class="sxs-lookup"><span data-stu-id="bd2e7-114">After you have finished, you will be able to enter values for the Message standard, Standard version, and Payload binding ID.</span></span> <span data-ttu-id="bd2e7-115">これらの値は CIDX Chem eStandards の仕様に含まれています。</span><span class="sxs-lookup"><span data-stu-id="bd2e7-115">You can find these values in the CIDX Chem eStandards specification.</span></span>  
  
## <a name="connecting-to-the-elemica-network"></a><span data-ttu-id="bd2e7-116">Elemica ネットワークへの接続</span><span class="sxs-lookup"><span data-stu-id="bd2e7-116">Connecting to the Elemica Network</span></span>  
 <span data-ttu-id="bd2e7-117">Microsoft のインストールを有効にすることができます[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]、Elemica に接続する[!INCLUDE[btsExchangeSvrNoVersion](../../includes/btsexchangesvrnoversion-md.md)]Provider (ESP)。</span><span class="sxs-lookup"><span data-stu-id="bd2e7-117">You can enable an installation of Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] to connect to the Elemica [!INCLUDE[btsExchangeSvrNoVersion](../../includes/btsexchangesvrnoversion-md.md)] Provider (ESP).</span></span> <span data-ttu-id="bd2e7-118">Elemica ネットワークで CIDX メッセージ交換を使用することで、化学工業分野における購入、売却、サプライチェーン管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="bd2e7-118">You can use the Elemica network for chemical-industry buying, selling, and supply-chain management using CIDX message exchange.</span></span>  
  
 <span data-ttu-id="bd2e7-119">[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] をカスタマイズし、Elemica Connectivity Pack のプロジェクト ファイルを使用して Elemica に接続します。</span><span class="sxs-lookup"><span data-stu-id="bd2e7-119">You customize [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] to connect to Elemica using project files in the Elemica Connectivity Pack.</span></span> <span data-ttu-id="bd2e7-120">Connectivity Pack をダウンロードする[ http://go.microsoft.com/fwlink/?LinkId=46195](http://go.microsoft.com/fwlink/?LinkId=46195)します。</span><span class="sxs-lookup"><span data-stu-id="bd2e7-120">You can download the Connectivity Pack from [http://go.microsoft.com/fwlink/?LinkId=46195](http://go.microsoft.com/fwlink/?LinkId=46195).</span></span> <span data-ttu-id="bd2e7-121">詳細については、MSDN のページで、"BizTalk Accelerator for RosettaNet 3.0 での Elemica ネットワークへの接続 』 ホワイト ペーパーを参照してください。 [ http://go.microsoft.com/fwlink/?linkid=46539](http://go.microsoft.com/fwlink/?linkid=46539)します。</span><span class="sxs-lookup"><span data-stu-id="bd2e7-121">For more information, see the “Connecting to the Elemica Network with BizTalk Accelerator for RosettaNet 3.0” white paper on MSDN at [http://go.microsoft.com/fwlink/?linkid=46539](http://go.microsoft.com/fwlink/?linkid=46539).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bd2e7-122">[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] に対して、ホワイト ペーパー『BizTalk Accelerator for RosettaNet 3.0 での Elemica ネットワークへの接続』の情報は有効です。</span><span class="sxs-lookup"><span data-stu-id="bd2e7-122">The information in the "Connecting to the Elemica Network with BizTalk Accelerator for RosettaNet 3.0" white paper is valid for [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)].</span></span>  
  
## <a name="cidx-procedures"></a><span data-ttu-id="bd2e7-123">CIDX の手順</span><span class="sxs-lookup"><span data-stu-id="bd2e7-123">CIDX Procedures</span></span>  
 <span data-ttu-id="bd2e7-124">CIDX メッセージ交換の設定方法については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="bd2e7-124">The following sections described how to set up CIDX message exchange:</span></span>  
  
-   [<span data-ttu-id="bd2e7-125">CIDX eStandards メッセージ交換のセットアップ</span><span class="sxs-lookup"><span data-stu-id="bd2e7-125">Setting Up CIDX eStandards Message Exchange</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md)  
  
-   [<span data-ttu-id="bd2e7-126">アグリーメントの作成と編集</span><span class="sxs-lookup"><span data-stu-id="bd2e7-126">Creating or Editing an Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)  
  
-   [<span data-ttu-id="bd2e7-127">XSD ベース PIP のインポート</span><span class="sxs-lookup"><span data-stu-id="bd2e7-127">Importing an XSD-based PIP</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/importing-an-xsd-based-pip.md)  
  
## <a name="see-also"></a><span data-ttu-id="bd2e7-128">参照</span><span class="sxs-lookup"><span data-stu-id="bd2e7-128">See Also</span></span>  
 <span data-ttu-id="bd2e7-129">[BizTalk Server に BizTalk Accelerator for RosettaNet の追加](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="bd2e7-129">[What BizTalk Accelerator for RosettaNet Adds to BizTalk Server](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md) </span></span>  
 [<span data-ttu-id="bd2e7-130">CIDX メッセージ規格</span><span class="sxs-lookup"><span data-stu-id="bd2e7-130">CIDX Messaging Standards</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/cidx-messaging-standards.md)