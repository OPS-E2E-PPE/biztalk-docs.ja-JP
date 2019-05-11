---
title: Microsoft BizTalk Accelerator for RosettaNet ドキュメント |Microsoft Docs
description: クイック リンクをインストールするには、開始、については、プログラミングし、ツール、管理、および BizTalk Server では、RosettaNet アクセラレータ (BTARN) のトラブルシューティング
caps.latest.revision: 7
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04c3a612-6cbc-4595-af81-dec3261803af
ms.author: mandia
ms.openlocfilehash: 78751bc59544ad33342a39db2fa9ded38cf00221
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282847"
---
# <a name="microsoft-biztalk-accelerator-for-rosettanet-documentation"></a><span data-ttu-id="b8233-103">Microsoft BizTalk Accelerator for RosettaNet ドキュメント</span><span class="sxs-lookup"><span data-stu-id="b8233-103">Microsoft BizTalk Accelerator for RosettaNet documentation</span></span>

 <span data-ttu-id="b8233-104">Microsoft BizTalk Server では、上のソリューションとしてビルド[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]RNIF 準拠のソリューションを開発するために必要なアプリケーションとプラットフォームを提供します。</span><span class="sxs-lookup"><span data-stu-id="b8233-104">Built as a solution on top of Microsoft BizTalk Server, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] provides the necessary applications and platform to develop RNIF-compliant solutions.</span></span> <span data-ttu-id="b8233-105">これらのソリューションでは、ユーザーが注文管理や在庫管理など、e ビジネス プロセスを自動化できるようにします。</span><span class="sxs-lookup"><span data-stu-id="b8233-105">These solutions let users automate their e-business processes, such as order management and inventory management.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="b8233-106">既存の活用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]XML を処理する機能および電子データは、企業間 (EDI) 通信を交換します。</span><span class="sxs-lookup"><span data-stu-id="b8233-106">takes advantage of the existing [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] functionality to process XML and electronic data interchange (EDI) communication among businesses.</span></span>  

<span data-ttu-id="b8233-107">このトピックでは、SDK サンプルおよびツール、読み取り、アクセラレータのしくみのステップバイ ステップ チュートリアルを使用して、RosettaNet をインストールする方法を含む、このドキュメントで取り上げるトピックの概要を提供します。</span><span class="sxs-lookup"><span data-stu-id="b8233-107">This topic provides an overview of the topics covered in this documentation, including how to install RosettaNet, provides step-by-step tutorials, read how the accelerator works, use the SDK samples and tools, and more.</span></span>

## <a name="install-or-upgrade"></a><span data-ttu-id="b8233-108">インストールまたはアップグレード</span><span class="sxs-lookup"><span data-stu-id="b8233-108">Install or upgrade</span></span>
<span data-ttu-id="b8233-109">[BizTalk Accelerator for RosettaNet にアップグレードをインストールまたは](install-configure-upgrade-uninstall-troubleshoot-rosettanet.md)インストールする手順、構成、アップグレード、および既知の問題があります。</span><span class="sxs-lookup"><span data-stu-id="b8233-109">[Install or upgrade the BizTalk Accelerator for RosettaNet](install-configure-upgrade-uninstall-troubleshoot-rosettanet.md) walks you through installing, configuration, upgrading, and also includes some known issues.</span></span>

## <a name="get-started"></a><span data-ttu-id="b8233-110">作業開始</span><span class="sxs-lookup"><span data-stu-id="b8233-110">Get started</span></span>
<span data-ttu-id="b8233-111">[BizTalk accelerator for RosettaNet 開始](get-started-with-biztalk-accelerator-for-rosettanet.md)このアクセラレータについて理解するためのいくつかのチュートリアルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b8233-111">[Get started with BizTalk Accelerator for RosettaNet](get-started-with-biztalk-accelerator-for-rosettanet.md) includes some tutorials to help you get familiar with this accelerator.</span></span>

## <a name="learn"></a><span data-ttu-id="b8233-112">学習する</span><span class="sxs-lookup"><span data-stu-id="b8233-112">Learn</span></span>
<span data-ttu-id="b8233-113">[RosettaNet アクセラレータの概要について説明します](learn-the-rosettanet-accelerator-and-the-biztalk-tools-available.md)について説明します、このアクセラレータの動作が使用できるいくつかのツールや CIDX メッセージ規格に説明します。</span><span class="sxs-lookup"><span data-stu-id="b8233-113">[Learn about the RosettaNet accelerator](learn-the-rosettanet-accelerator-and-the-biztalk-tools-available.md) explains how this accelerators works, describes some tools you can use, the CIDX messaging standards, and more.</span></span>

## <a name="programming-and-tooling"></a><span data-ttu-id="b8233-114">プログラミングとツール</span><span class="sxs-lookup"><span data-stu-id="b8233-114">Programming and tooling</span></span>
<span data-ttu-id="b8233-115">[プログラミング ガイド、SDK ツール、およびサンプル](programming-guide-SDK-tools-and-samples.md)プライベート プロセスをカスタマイズし、Pip を操作して、BTARN のツールを使用 SDK サンプルをデプロイする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b8233-115">[Programming guide, SDK tools and samples](programming-guide-SDK-tools-and-samples.md) shows you how to customize private processes, work with PIPs, use the BTARN tools, and deploy the SDK samples.</span></span> 

## <a name="manage-configuration-certificates-databases-and-security"></a><span data-ttu-id="b8233-116">構成、証明書、データベース、およびセキュリティを管理します。</span><span class="sxs-lookup"><span data-stu-id="b8233-116">Manage configuration, certificates, databases, and security</span></span>
<span data-ttu-id="b8233-117">[構成、証明書、データベース、およびセキュリティを管理](manage-configuration-certificates-databases-security.md)CIDX ソリューションのセットアップ、BTARN の構成の管理方法の詳細を含む証明書と、データベース、およびセキュリティを管理します。</span><span class="sxs-lookup"><span data-stu-id="b8233-117">[Manage configuration, certificates, databases, and security](manage-configuration-certificates-databases-security.md) including details on administering your BTARN configuration, setting up a CIDX solution, managing certificates and the database, and security.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="b8233-118">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b8233-118">Troubleshooting</span></span>
<span data-ttu-id="b8233-119">[トラブルシューティングと既知の問題](troubleshooting-and-known-issues-in-rosettanet.md)の一般的なエラーの詳細を説明し、通知エラー、BAM、インストールと構成、および詳細に関する既知の問題を一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="b8233-119">[Troubleshooting and known issues](troubleshooting-and-known-issues-in-rosettanet.md) provides details on common errors, and lists known issues with notification failures, BAM, installation and configuration, and more.</span></span>

## <a name="online-community"></a><span data-ttu-id="b8233-120">オンライン コミュニティ</span><span class="sxs-lookup"><span data-stu-id="b8233-120">Online community</span></span>  
 <span data-ttu-id="b8233-121">オンライン コミュニティ ディスカッションに参加するに移動[BizTalk アダプターのフォーラム](https://social.msdn.microsoft.com/Forums/en-US/home?forum=biztalkr2adapters)</span><span class="sxs-lookup"><span data-stu-id="b8233-121">To participate in the online community discussions, go to [BizTalk adapters forum](https://social.msdn.microsoft.com/Forums/en-US/home?forum=biztalkr2adapters)</span></span>