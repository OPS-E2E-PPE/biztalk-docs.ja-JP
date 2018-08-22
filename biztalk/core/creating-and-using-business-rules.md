---
title: ビジネス ルールの作成と |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, Business Rules Editor
- Business Rules Editor
ms.assetid: a15fd09b-ff4e-4c26-8cb6-5ffd258a2182
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9d01e5eaf96c6490c68424fd09e297e0e60ef9d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979395"
---
# <a name="creating-and-using-business-rules"></a>ビジネス ルールの作成および使用
ビジネス ルール (またはビジネス ポリシー) は、組織の構造、活動、および戦略を定義し、制御するものです。 ビジネス ルールは手順書や契約書などで正式に規定されている場合もあれば、従業員の知識や専門知識として存在する場合もあります。 ビジネス ルールは動的で時間と共に変化し、すべての種類のアプリケーションで使用されます。 金融保険、e ビジネス、輸送、電気通信、Web ベースのサービス、パーソナル化などは、ビジネス ルールによって統制される数多くのビジネス分野のごく一部に過ぎません。 これらのビジネス分野が共通して抱えているニーズは、ビジネス上の戦略、ポリシー、および規定を情報技術 (IT) 担当者に伝えてソフトウェア アプリケーションに組み込むことです。  
  
 C、C++、Microsoft Visual Basic などの従来の手続き型言語およびオブジェクト指向言語は、プログラマ指向です。 Java や C# などの高度なオブジェクト指向言語も、主にプログラマのための言語です。 設計、開発、コンパイル、テストで構成される従来のソフトウェア開発サイクルには、かなりの時間と調整が必要であり、自動化されたビジネス ポリシーの保守にプログラマ以外が参加するのは不可能です。 ビジネス ルール フレームワークは、この問題に対処するために、時間のかかる従来のアプリケーション プログラミング サイクルを排除した高速なアプリケーション作成を可能にする開発環境を提供します。 たとえば、このフレームワークを使用して構築されたビジネス ポリシーを更新する場合は、関連するオーケストレーションを再コンパイルおよび再展開する必要がありません。  
  
 ビジネス ルール フレームワークは Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] と緊密に統合されているため、開発者は次の機能を利用してビジネス ルールを構築し、管理できます。  
  
- ビジネス ルールを評価する推論メカニズムを実装したパフォーマンスに優れたルール エンジン。  
  
- ルールベースのアプリケーションを開発するための機能豊富な一連のアプリケーション プログラミング インターフェイス (API)。  
  
- グラフィカル ユーザー インターフェイスであるビジネス ルール作成ツール。開発者、ビジネス アナリスト、および管理者はこのツールをさまざまに使用して、ルールやポリシーを効率的に開発し、適用できます。  
  
- BizTalk オーケストレーションとのシームレスな統合。これにより、ビジネス ポリシーやビジネス ルールのセットを BizTalk オーケストレーションから呼び出すことができます。  
  
- ルール エンジン展開ウィザード。ビジネス ルールまたはそれらのルールが使用するボキャブラリのインポートとエクスポート、およびそれらのルールの展開と展開解除を迅速に行うことができます。  
  
  次の図に示すように、ビジネス ルール フレームワークを使って作成したビジネス ルール (ポリシー) は、オーケストレーションに基づくビジネス プロセスで使用できます。  
  
  ![プロセスでビジネス ポリシーを示す図。](../core/media/ebiz-dev-busprcsi.gif "ebiz_dev_busprcsi")  
  ビジネス ポリシー  
  
  このセクションでは、ビジネス ルール フレームワークの活用方法、および [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 付属のツールを使用してビジネス ルールを開発する方法に関する概要を説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [ビジネス ルールの作成](../core/creating-business-rules-using-the-business-rule-composer.md)  
  
-   [ビジネス ルール フレームワークのセキュリティ](../core/business-rules-framework-security.md)  
  
-   [ビジネス ルール フレームワークによるプログラミング](../core/programming-with-business-rules-framework.md)  
  
-   [ルール エンジンの構成およびチューニング パラメーター](../core/rule-engine-configuration-and-tuning-parameters.md)