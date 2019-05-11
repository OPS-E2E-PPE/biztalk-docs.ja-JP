---
title: オーケストレーションを構築する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- building, orchestrations
- building, solutions
- building, projects
- solutions, building
- projects, building
- orchestrations, building
ms.assetid: f12d5da0-fbae-4f0e-85bf-1ca2e9bf7d62
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f755ea3b2aa01919d7f5d40a9eca92fd3529c629
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387075"
---
# <a name="how-to-build-orchestrations"></a>オーケストレーションを構築する方法
描画オーケストレーションを完了すると後、は、実行可能ファイルのオーケストレーションをカプセル化するアセンブリに、BizTalk プロジェクトをビルドします。  
  
 ビルド プロセス中には、BizTalk オーケストレーション デザイナーが完全で正しい、しでない場合は、タスク一覧のエラーを報告するかどうかを判断するには、各図形を調べます。  
  
 Visual Studio で構築するためのいくつかのオプションがあります。  
  
- オーケストレーションが存在するソリューション全体をビルドすることができます。  
  
- ソリューション内の 1 つのプロジェクトをビルドすることができます。  
  
- プロジェクトまたはソリューションを構築するときに、オーケストレーションをスキップできます。  
  
  他のオーケストレーションを含む、他のコンポーネントを作成する場合、特定のオーケストレーションをビルドしたくない場合は、ビルドしたくないとはスキップされるオーケストレーションの .odx ファイルのファイルのプロパティで指定できます。  
  
### <a name="to-build-an-orchestration"></a>オーケストレーションを構築するには  
  
-   オーケストレーションを作成した後は、テストしたり、オーケストレーションを使用する前に、それを含んでいる BizTalk プロジェクトをビルドする必要があります。 ソリューション全体、またはソリューション内の 1 つのプロジェクトをビルドすることができます。  
  
### <a name="to-build-a-solution"></a>ソリューションを構築するには  
  
-   ソリューション エクスプ ローラーでソリューションを右クリックし、選択**ソリューションのビルド**します。  
  
### <a name="to-build-a-project"></a>プロジェクトをビルドします。  
  
-   プロジェクトを右クリックして**ビルド**します。  
  
### <a name="to-build-a-project-or-solution-without-compiling-a-particular-orchestration"></a>特定のオーケストレーションをコンパイルせずに、プロジェクトまたはソリューションを構築するには  
  
-   対応する .odx ファイルとプロパティ ウィンドウで、オーケストレーションをクリックし、**ビルド アクション**プロパティと選択**None**します。