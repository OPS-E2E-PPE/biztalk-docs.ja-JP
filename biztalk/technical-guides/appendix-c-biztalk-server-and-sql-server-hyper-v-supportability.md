---
title: "付録 c: BizTalk Server と SQL Server の HYPER-V のサポート性 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 05bc03d4-8fe7-490d-84e2-05dae7a7441e
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20cd40f642c61b124b16bdca8431eb94a4b1cf91
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="appendix-c-biztalk-server-and-sql-server-hyper-v-supportability"></a><span data-ttu-id="38260-102">付録 c: BizTalk Server と SQL Server の HYPER-V のサポート</span><span class="sxs-lookup"><span data-stu-id="38260-102">Appendix C: BizTalk Server and SQL Server Hyper-V Supportability</span></span>
<span data-ttu-id="38260-103">テストのシナリオ」に記載[BizTalk サーバー仮想化のパフォーマンスのテスト](../technical-guides/testing-biztalk-server-virtualization-performance.md)で実行した[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]と[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="38260-103">The test scenarios described in [Testing BizTalk Server Virtualization Performance](../technical-guides/testing-biztalk-server-virtualization-performance.md) were performed with [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] and [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)].</span></span> [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]<span data-ttu-id="38260-104">Microsoft Virtual Server 2005 で実行されているか、サポート対象のオペレーティング システムにインストールされている場合にサポート[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]HYPER-V です。</span><span class="sxs-lookup"><span data-stu-id="38260-104"> is supported when installed on a supported operating system that is running on Microsoft Virtual Server 2005 or on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] Hyper-V.</span></span> <span data-ttu-id="38260-105">詳細については、Microsoft サポート技術情報記事「Microsoft BizTalk Server は仮想マシンでサポート性」を参照していただけます[http://go.microsoft.com/fwlink/?LinkId=148941](http://go.microsoft.com/fwlink/?LinkId=148941)です。</span><span class="sxs-lookup"><span data-stu-id="38260-105">For more information, see the Microsoft Knowledge Base article “Microsoft BizTalk Server supportability on a virtual machine” available at [http://go.microsoft.com/fwlink/?LinkId=148941](http://go.microsoft.com/fwlink/?LinkId=148941).</span></span>  
  
 <span data-ttu-id="38260-106">サポート ポリシー[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]で実行されているサポートされたオペレーティング システムにインストールされているときに[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]HYPER-V が Microsoft サポート技術情報記事ハードウェアで実行されている Microsoft SQL Server 製品のサポート ポリシー」に記載されています。"仮想化環境で使用可能な[http://go.microsoft.com/fwlink/?LinkId=148942](http://go.microsoft.com/fwlink/?LinkId=148942)です。</span><span class="sxs-lookup"><span data-stu-id="38260-106">Support policy for [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] when installed on a supported operating system that is running on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] Hyper-V is documented in the Microsoft Knowledge Base article “Support policy for Microsoft SQL Server products that are running in a hardware virtualization environment” available at [http://go.microsoft.com/fwlink/?LinkId=148942](http://go.microsoft.com/fwlink/?LinkId=148942).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="38260-107">このガイドの執筆時点で、SQL Server インスタンスのクラスタ リングを HYPER-V 環境をサポートされているシナリオでされていません。</span><span class="sxs-lookup"><span data-stu-id="38260-107">As of the writing of this guide, clustering of a SQL Server instance on a Hyper-V environment is not a supported scenario.</span></span>