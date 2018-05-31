---
title: 動的ルーティングを使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: caa3a35f-cafa-4524-8b96-f8a333b7ff87
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38b668f53ba87a461441b0dbb498ae0677fa5956
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295698"
---
# <a name="using-dynamic-routing"></a>動的ルーティングを使用します。
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]組み込みプロセスと、一般的な配布エージェントを使用してメッセージの動的なルーティングをサポートしている ESB ディスパッチャーまたは ESB ディスパッチャーの逆アセンブル パイプライン コンポーネントを使用して、メッセージング レイヤーでのメッセージの動的ルーティングもサポートします。  
  
## <a name="overview"></a>概要  
 動的解決のメカニズムで[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]メッセージが到着したときに、またはメッセージが配信される前にすぐにエンドポイントの探索を有効にします。  
  
## <a name="how-it-works"></a>しくみ  
 提供される一般的な配布エージェント、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サンプルであり、開発と動的ルーティング手法の利用をガイドします。 簡単に追加の配信エージェントを作成したり、送信ポートのみで構成される配信エージェント (これは、オーケストレーションを実装していません) を実装できます。 既定では、ESB ディスパッチと ESB ディスパッチ逆アセンブラー パイプライン コンポーネントは、非常に最適化動的ルーティング機能を提供します。  
  
 一般的な配布エージェント自体がメッセージをサブスクライブするオーケストレーションを実装する場所、**名前**、現在の属性**ServiceInstance**旅行計画内の要素は**Microsoft.Practices.ESB.Services.Routing**です。 エージェントでは、次の操作手順を実行します。  
  
1.  型指定されていないメッセージ (system.xml.xmldocument など) を受け取ります。  
  
2.  N 個の競合回避モジュールのマネージャーを使用してエンドポイントを解決しようとします。  
  
3.  アダプター マネージャーを使用してメッセージのコンテキストと論理の動的なポートのエンドポイント プロパティを設定します。  
  
4.  さらにメッセージのルーティング用の動的送信ポートの BizTalk Server サブスクリプションをトリガーする、直接バインドの送信ポートでメッセージを発行します。  
  
## <a name="how-to-configure-dynamic-routing"></a>動的ルーティングを構成する方法  
 行程デザイナーを使用して動的ルーティングを構成する方法の詳細については、「行程のデザイナーを使用して日程を作成するを参照してください。  
  
## <a name="dynamic-routing-errors"></a>動的ルーティング エラー  
 動的ルーティング メカニズムを作成し、発行、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]次の場合、エラー メッセージ。  
  
-   配信エージェントは、・ イン タイム (JIT) の解決時にエンドポイントを決定することはできません。  
  
-   配信エラーが発生します。  
  
-   出力メッセージのサブスクライバーが存在しません。  
  
-   すべてのシステム例外が発生します。