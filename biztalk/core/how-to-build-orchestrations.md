---
title: オーケストレーションを構築する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 79e91ec6ecfa061aa4621effba9a1f868cad5d96
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248146"
---
# <a name="how-to-build-orchestrations"></a>オーケストレーションのビルド方法
オーケストレーションをデザインしたら、BizTalk プロジェクトを、実行可能なオーケストレーションが格納されたアセンブリとしてビルドします。  
  
 ビルド プロセスでは、BizTalk オーケストレーション デザイナーが各図形を検査し、不備があった場合は、タスク一覧にエラーとして表示します。  
  
 Visual Studio には、次のようなビルド オプションがあります。  
  
-   オーケストレーションの存在するソリューション全体をビルドする。  
  
-   ソリューション内の単一のプロジェクトをビルドする。  
  
-   プロジェクトまたはソリューションのビルド時に特定のオーケストレーションをスキップする。  
  
 他のコンポーネント (他のオーケストレーションも含む) をビルドするとき、特定のオーケストレーションだけはビルドの対象外にしたい場合があります。このような場合は、オーケストレーションの .odx ファイルのプロパティでビルドの対象外として指定することにより、そのオーケストレーションのビルドをスキップさせることができます。  
  
### <a name="to-build-an-orchestration"></a>オーケストレーションをビルドするには  
  
-   完成したオーケストレーションをテストしたり、実際に運用したりするためには、そのオーケストレーションが含まれる BizTalk プロジェクトをビルドする必要があります。 ソリューション全体をビルドすることも、ソリューション内の単一のプロジェクトだけをビルドすることもできます。  
  
### <a name="to-build-a-solution"></a>ソリューションをビルドするには  
  
-   ソリューション エクスプ ローラーでソリューションを右クリックし、**ソリューションのビルド**です。  
  
### <a name="to-build-a-project"></a>プロジェクトをビルドするには  
  
-   プロジェクトを右クリックし **ビルド**です。  
  
### <a name="to-build-a-project-or-solution-without-compiling-a-particular-orchestration"></a>特定のオーケストレーションをコンパイルから除外してプロジェクトまたはソリューションをビルドするには  
  
-   対応する .odx ファイルとプロパティ ウィンドウで、オーケストレーションをクリックし、をクリックして、**ビルド アクション**プロパティを選択**None**です。