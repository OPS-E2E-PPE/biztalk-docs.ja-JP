---
title: "BizTalk Server 2010 Accelerator for SWIFT のインストール |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 78d996ce-40ea-4d01-b083-c55ccace4b26
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8dcec7f25211fac8c99a89ce7ce85840f457971a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="installing-biztalk-server-2010-accelerator-for-swift"></a><span data-ttu-id="acc37-102">BizTalk Server 2010 Accelerator for SWIFT をインストールする</span><span class="sxs-lookup"><span data-stu-id="acc37-102">Installing BizTalk Server 2010 Accelerator for SWIFT</span></span>
<span data-ttu-id="acc37-103">![ロゴ](../technical-guides/media/bts-10-installaccelerator-logo.gif "BTS_10_InstallAccelerator_Logo")</span><span class="sxs-lookup"><span data-stu-id="acc37-103">![Logo](../technical-guides/media/bts-10-installaccelerator-logo.gif "BTS_10_InstallAccelerator_Logo")</span></span>  
  
 <span data-ttu-id="acc37-104">BizTalk の技術記事</span><span class="sxs-lookup"><span data-stu-id="acc37-104">BizTalk Technical Article</span></span>  
  
 <span data-ttu-id="acc37-105">**BizTalk Server 2010 Accelerator for SWIFT のインストール**</span><span class="sxs-lookup"><span data-stu-id="acc37-105">**Installing BizTalk Server 2010 Accelerator for SWIFT**</span></span>  
  
 <span data-ttu-id="acc37-106">**ライター:** Maria Quian、米国 Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="acc37-106">**Writer:** Maria Quian, Microsoft Corporation</span></span>  
  
 <span data-ttu-id="acc37-107">**技術レビューアー:** Andres Naranjo、Mandi Ohlinger</span><span class="sxs-lookup"><span data-stu-id="acc37-107">**Technical Reviewers:** Andres Naranjo, Mandi Ohlinger</span></span>  
  
 <span data-ttu-id="acc37-108">**公開:** 2012 年 6 月</span><span class="sxs-lookup"><span data-stu-id="acc37-108">**Published:** June 2012</span></span>  
  
 <span data-ttu-id="acc37-109">**適用対象:** BizTalk Server 2010 Accelerator for SWIFT</span><span class="sxs-lookup"><span data-stu-id="acc37-109">**Applies To:** BizTalk Server 2010 Accelerator for SWIFT</span></span>  
  
 <span data-ttu-id="acc37-110">**概要:** Microsoft BizTalk Server 2010 Accelerator for SWIFT (A4SWIFT) のインストールが成功するための基礎は、A4SWIFT の機能および各機能が依存している BizTalk コンポーネントについて理解します。</span><span class="sxs-lookup"><span data-stu-id="acc37-110">**Summary:** The foundation for a successful installation of Microsoft BizTalk Server 2010 Accelerator for SWIFT (A4SWIFT) is an understanding of the A4SWIFT features and the BizTalk components on which each feature depends.</span></span> <span data-ttu-id="acc37-111">各 A4SWIFT の機能は、正しく構成されているその他の BizTalk コンポーネントに依存します。</span><span class="sxs-lookup"><span data-stu-id="acc37-111">Each A4SWIFT feature depends on other properly configured BizTalk components.</span></span> <span data-ttu-id="acc37-112">他の考慮事項に影響を与える A4SWIFT 環境を構築するには、既存のネットワーク インフラストラクチャと構成済みの BizTalk Server 環境が含まれます。</span><span class="sxs-lookup"><span data-stu-id="acc37-112">Other considerations that affect building an A4SWIFT environment include an existing network infrastructure and an already configured BizTalk Server environment.</span></span> <span data-ttu-id="acc37-113">このドキュメントは参照し、BizTalk Server 環境を作成するため、既存のドキュメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="acc37-113">This document will refer and use the existing documentation for building BizTalk Server environments.</span></span> <span data-ttu-id="acc37-114">A4SWIFT は、BizTalk Server 2010 のすべてのソフトウェアとハードウェア要件を継承します。</span><span class="sxs-lookup"><span data-stu-id="acc37-114">A4SWIFT inherits all software and hardware requirements for BizTalk Server 2010.</span></span>  
  
 <span data-ttu-id="acc37-115">インストール ガイドでは、各 A4SWIFT 関連コンポーネントですが単一コンパイルされた文書ではなく、インストールと構成手順について詳しく説明を使用できます。</span><span class="sxs-lookup"><span data-stu-id="acc37-115">An installation guide is available for each A4SWIFT related component but not a single compiled document that elaborates on the installation/configuration steps.</span></span> <span data-ttu-id="acc37-116">このドキュメントはこれらをまとめるためと、いくつかのインストールと構成の中に発生した一般的な問題を識別します。</span><span class="sxs-lookup"><span data-stu-id="acc37-116">This document will bring them together and identify some of the common issues encountered during installation and configuration.</span></span>  
  
 <span data-ttu-id="acc37-117">ダウンロード ドキュメントを参照してください、[をインストールする BizTalk Server 2010 Accelerator for SWIFT](http://go.microsoft.com/fwlink/?LinkId=255118) Word 文書です。</span><span class="sxs-lookup"><span data-stu-id="acc37-117">To review the document, please download the [Installing BizTalk Server 2010 Accelerator for SWIFT](http://go.microsoft.com/fwlink/?LinkId=255118) Word document.</span></span>