---
title: BizTalk Server 2010 Accelerator for SWIFT のインストール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 78d996ce-40ea-4d01-b083-c55ccace4b26
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9a68a49d89f31e3a025933c47c6475ee53aa0df
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65277127"
---
# <a name="installing-biztalk-server-2010-accelerator-for-swift"></a><span data-ttu-id="09a18-102">Installing BizTalk Server 2010 Accelerator for SWIFT</span><span class="sxs-lookup"><span data-stu-id="09a18-102">Installing BizTalk Server 2010 Accelerator for SWIFT</span></span>
<span data-ttu-id="09a18-103">![Logo](../technical-guides/media/bts-10-installaccelerator-logo.gif "BTS_10_InstallAccelerator_Logo")</span><span class="sxs-lookup"><span data-stu-id="09a18-103">![Logo](../technical-guides/media/bts-10-installaccelerator-logo.gif "BTS_10_InstallAccelerator_Logo")</span></span>  
  
 <span data-ttu-id="09a18-104">BizTalk の技術記事</span><span class="sxs-lookup"><span data-stu-id="09a18-104">BizTalk Technical Article</span></span>  
  
 <span data-ttu-id="09a18-105">**BizTalk Server 2010 Accelerator for SWIFT のインストール**</span><span class="sxs-lookup"><span data-stu-id="09a18-105">**Installing BizTalk Server 2010 Accelerator for SWIFT**</span></span>  
  
 <span data-ttu-id="09a18-106">**ライター:** Maria Quian、Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="09a18-106">**Writer:** Maria Quian, Microsoft Corporation</span></span>  
  
 <span data-ttu-id="09a18-107">**技術校閲者:** Andres Naranjo、Mandi Ohlinger</span><span class="sxs-lookup"><span data-stu-id="09a18-107">**Technical Reviewers:** Andres Naranjo, Mandi Ohlinger</span></span>  
  
 <span data-ttu-id="09a18-108">**公開日。** 2012 年 6 月</span><span class="sxs-lookup"><span data-stu-id="09a18-108">**Published:** June 2012</span></span>  
  
 <span data-ttu-id="09a18-109">**適用対象します。** BizTalk Server 2010 Accelerator for SWIFT</span><span class="sxs-lookup"><span data-stu-id="09a18-109">**Applies To:** BizTalk Server 2010 Accelerator for SWIFT</span></span>  
  
 <span data-ttu-id="09a18-110">**概要:** Microsoft BizTalk Server 2010 Accelerator for SWIFT (A4SWIFT) のインストールが成功の基盤は、A4SWIFT の機能と各機能が依存する BizTalk コンポーネントの理解。</span><span class="sxs-lookup"><span data-stu-id="09a18-110">**Summary:** The foundation for a successful installation of Microsoft BizTalk Server 2010 Accelerator for SWIFT (A4SWIFT) is an understanding of the A4SWIFT features and the BizTalk components on which each feature depends.</span></span> <span data-ttu-id="09a18-111">A4SWIFT の各機能は、適切に構成されたその他の BizTalk コンポーネントに依存します。</span><span class="sxs-lookup"><span data-stu-id="09a18-111">Each A4SWIFT feature depends on other properly configured BizTalk components.</span></span> <span data-ttu-id="09a18-112">A4SWIFT 環境の構築に影響するその他の考慮事項には、既存のネットワーク インフラストラクチャと構成済みの BizTalk Server 環境が含まれます。</span><span class="sxs-lookup"><span data-stu-id="09a18-112">Other considerations that affect building an A4SWIFT environment include an existing network infrastructure and an already configured BizTalk Server environment.</span></span> <span data-ttu-id="09a18-113">このドキュメントは参照し、BizTalk Server 環境を構築するために既存のドキュメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="09a18-113">This document will refer and use the existing documentation for building BizTalk Server environments.</span></span> <span data-ttu-id="09a18-114">A4SWIFT では、BizTalk Server 2010 のすべてのソフトウェアとハードウェア要件を継承します。</span><span class="sxs-lookup"><span data-stu-id="09a18-114">A4SWIFT inherits all software and hardware requirements for BizTalk Server 2010.</span></span>  
  
 <span data-ttu-id="09a18-115">インストール ガイドでは、各 A4SWIFT 関連コンポーネントですが、1 つコンパイルされたドキュメントではなく、インストール/構成手順について詳しく説明する使用できます。</span><span class="sxs-lookup"><span data-stu-id="09a18-115">An installation guide is available for each A4SWIFT related component but not a single compiled document that elaborates on the installation/configuration steps.</span></span> <span data-ttu-id="09a18-116">このドキュメントはそれらをまとめると、いくつかのインストールと構成の中に発生した一般的な問題を識別します。</span><span class="sxs-lookup"><span data-stu-id="09a18-116">This document will bring them together and identify some of the common issues encountered during installation and configuration.</span></span>  
  
 <span data-ttu-id="09a18-117">ドキュメントを確認するには、ダウンロード、[をインストールする BizTalk Server 2010 Accelerator for SWIFT](http://go.microsoft.com/fwlink/?LinkId=255118) Word 文書です。</span><span class="sxs-lookup"><span data-stu-id="09a18-117">To review the document, please download the [Installing BizTalk Server 2010 Accelerator for SWIFT](http://go.microsoft.com/fwlink/?LinkId=255118) Word document.</span></span>