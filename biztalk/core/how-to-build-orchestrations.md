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
ms.openlocfilehash: 9000c986e95270328d9c31ef4f5e3bda7f1576e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987331"
---
# <a name="how-to-build-orchestrations"></a>オーケストレーションのビルド方法
オーケストレーションをデザインしたら、BizTalk プロジェクトを、実行可能なオーケストレーションが格納されたアセンブリとしてビルドします。  
  
 ビルド プロセスでは、BizTalk オーケストレーション デザイナーが各図形を検査し、不備があった場合は、タスク一覧にエラーとして表示します。  
  
 Visual Studio には、次のようなビルド オプションがあります。  
  
- オーケストレーションの存在するソリューション全体をビルドする。  
  
- ソリューション内の単一のプロジェクトをビルドする。  
  
- プロジェクトまたはソリューションのビルド時に特定のオーケストレーションをスキップする。  
  
  他のコンポーネント (他のオーケストレーションも含む) をビルドするとき、特定のオーケストレーションだけはビルドの対象外にしたい場合があります。このような場合は、オーケストレーションの .odx ファイルのプロパティでビルドの対象外として指定することにより、そのオーケストレーションのビルドをスキップさせることができます。  
  
### <a name="to-build-an-orchestration"></a>オーケストレーションをビルドするには  
  
-   完成したオーケストレーションをテストしたり、実際に運用したりするためには、そのオーケストレーションが含まれる BizTalk プロジェクトをビルドする必要があります。 ソリューション全体をビルドすることも、ソリューション内の単一のプロジェクトだけをビルドすることもできます。  
  
### <a name="to-build-a-solution"></a>ソリューションをビルドするには  
  
-   ソリューション エクスプ ローラーでソリューションを右クリックし、選択**ソリューションのビルド**します。  
  
### <a name="to-build-a-project"></a>プロジェクトをビルドします。  
  
-   プロジェクトを右クリックして**ビルド**します。  
  
### <a name="to-build-a-project-or-solution-without-compiling-a-particular-orchestration"></a>特定のオーケストレーションをコンパイルから除外してプロジェクトまたはソリューションをビルドするには  
  
-   対応する .odx ファイルとプロパティ ウィンドウで、オーケストレーションをクリックし、**ビルド アクション**プロパティと選択**None**します。