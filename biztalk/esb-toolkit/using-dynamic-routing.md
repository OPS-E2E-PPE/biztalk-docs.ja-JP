---
title: 動的ルーティングを使用して |Microsoft Docs
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
ms.openlocfilehash: e30d13458e9c020f66984f42d3a472364bc8b425
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396458"
---
# <a name="using-dynamic-routing"></a>動的ルーティングを使用します。
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]組み込みプロセスと、一般的な配布エージェントを使用してメッセージの動的なルーティングをサポートしている ESB ディスパッチャーまたは ESB ディスパッチャー逆アセンブル パイプライン コンポーネントを使用して、メッセージング層でのメッセージの動的ルーティングもサポートされます。  
  
## <a name="overview"></a>概要  
 動的解決メカニズムは[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]メッセージが届いたとき、またはメッセージが配信される前にすぐにエンドポイントの探索を有効にします。  
  
## <a name="how-it-works"></a>しくみ  
 提供される一般的な配布エージェント、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サンプルであり、開発と動的ルーティングの手法の使用方法のガイド。 エージェントの追加の配信を作成したり、(これは、オーケストレーションを実装していません) の送信ポートのみで構成される配信エージェントを実装したりすることができます簡単にします。 既定では、ESB のディスパッチと ESB ディスパッチ逆アセンブラー パイプライン コンポーネントは、非常に動的ルーティング機能をより最適化されたを提供します。  
  
 汎用的な配信エージェント自体がメッセージをサブスクライブするオーケストレーションを実装する場所、**名前**、現在の属性**ServiceInstance**旅行計画内の要素が**Microsoft.Practices.ESB.Services.Routing**します。 エージェントは、次の一連の操作を実行します。  
  
1.  型指定されていないメッセージ (System.Xml.XmlDocument) を受け取ります。  
  
2.  N 個の競合回避モジュールのマネージャーを使用してエンドポイントを解決しようとします。  
  
3.  アダプター マネージャーを使用して、メッセージ コンテキストと論理の動的ポートのエンドポイントのプロパティを設定します。  
  
4.  さらにメッセージのルーティングに動的送信ポートでの BizTalk Server サブスクリプションをトリガーする、直接バインドされた送信ポートでメッセージを公開します。  
  
## <a name="how-to-configure-dynamic-routing"></a>動的ルーティングを構成する方法  
 旅行プラン デザイナーを使用して動的ルーティングを構成する方法の詳細については、旅行プランを使用してスケジュールの作成のデザイナーを参照してください。  
  
## <a name="dynamic-routing-errors"></a>動的ルーティング エラー  
 動的ルーティング メカニズムを作成し、発行、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]次の場合にエラー メッセージ。  
  
-   配信エージェントは、ジャストイン タイム (JIT) の解決時にエンドポイントを決定することはできません。  
  
-   配信エラーが発生します。  
  
-   出力メッセージのサブスクライバーが存在しません。  
  
-   すべてのシステム例外が発生します。