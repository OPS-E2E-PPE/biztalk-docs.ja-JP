---
title: 展開の準備 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, planning
ms.assetid: 437caa31-f7f8-42e0-af1f-13aaee0955cd
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d7b6f0677b542ad03b2109eddb3352924f6b59c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966499"
---
# <a name="preparing-for-deployment"></a>展開の準備
このセクションでは、展開の計画と準備の段階についてを説明します。 展開を実装する前に次の準備を行います。  
  
1. 読み取りと、既知の問題を理解し、機器を準備します。  
  
   -   ハードウェアとソフトウェアの展開とネットワーク ダイアグラムとデプロイ ワークシート (ネットワークの図と選択した展開アーキテクチャに基づいて) 展開のバリエーションを反映するために必要なチェックリストを作成します。  
  
   -   ハードウェアおよびソフトウェアのチェックリストを取得します。 この買収には、すべてのサービス パック、修正プログラム、および展開に必要なソフトウェア更新プログラムのダウンロードが含まれています。  
  
        インターネットにアクセスできるコンピューターを使用してこれらのソフトウェア コンポーネントをダウンロードして、これらのソフトウェア コンポーネントを簡単に配布の CD-ROM にコピーします。  
  
2. さまざまな段階に、デプロイを分離し、各ステージに関連付けられているタスクを識別します。 この戦略では、特定の展開の段階に従ってタスクを整理することによって、展開プロセスを簡略化します。 たとえば、所定の展開には、次のサーバー展開の段階が含まれています。  
  
3. ドメイン コント ローラーを構成します。  
  
4. データベースの構成 (実行時間を含む[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]クラスターおよびデザイン時のデータベース サーバー)。  
  
5. BizTalk server を構成します。  
  
   このセクションには、次のトピックが含まれています。  
  
-   [ネットワーク要件](../../adapters-and-accelerators/accelerator-swift/network-requirements.md)  
  
-   [展開のためのハードウェア要件とソフトウェア要件](../../adapters-and-accelerators/accelerator-swift/hardware-and-software-requirements-for-deployment.md)