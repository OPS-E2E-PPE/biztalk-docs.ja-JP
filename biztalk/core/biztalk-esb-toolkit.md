---
title: BizTalk ESB Toolkit |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 08035518-17ad-44d2-ab06-90d725c95ced
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 535fd99ee5c1b9f9c25dd49e2a2441acb855c78a
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "22231890"
---
# <a name="biztalk-esb-toolkit"></a>BizTalk ESB Toolkit
Microsoft BizTalk ESB Toolkit は、Microsoft BizTalk Server を使用して疎結合のメッセージング アーキテクチャをサポートしています。 BizTalk Server には、メッセージング アプリケーション用の強力なパブリッシュ/サブスクライブ メカニズムが組み込まれています。このメカニズムは、サブスクリプションを作成および入力することによって機能し、サービス指向アーキテクチャ (SOA) アプリケーション向けの、高い効率と拡張性を備えたプラットフォームを提供します。 BizTalk ESB Toolkit は、BizTalk Server の機能を拡張して、次のようなアプリケーションの構築に焦点を合わせたさまざまな新機能を提供します。そのアプリケーションとは、スケジュールに基づくサービス呼び出しによる軽量なサービス作成、エンドポイントやマップの動的な解決、Web サービスと WS-* の統合、障害管理と報告、およびサードパーティの SOA 管理ソリューションとの統合を組み込んだ、堅牢な接続型のサービス指向アプリケーションです。  
  
## <a name="overview"></a>概要  
 BizTalk ESB Toolkit は、アーキテクチャに関するガイダンス、パターン、および BizTalk Server コンポーネントと .NET Framework コンポーネントのコレクションを提供します。BizTalk ESB Toolkit を使用すると、Microsoft プラットフォームでの Enterprise Service Bus (ESB) の開発が簡素化され、Microsoft ユーザーは独自のメッセージング ソリューションや統合ソリューションを拡張できます。  
  
## <a name="common-scenarios"></a>一般的なシナリオ  
 Enterprise Service Bus (ESB) という用語は、サービス指向アーキテクチャ (SOA) を実現するためのインフラストラクチャの実装というコンテキストにおいて広く利用されています。 しかし、SOA の開発にかかわった実際の経験から、ESB は包括的なサービス指向インフラストラクチャ (SOI) を構成する多数の構成要素の 1 つにすぎないことが判明しています。 ESB という用語は数多くの多様な方向に変貌し、その定義は、個々の ESB ベンダーおよび統合プラットフォーム ベンダーによって、また、特定の SOA イニシアティブの要件によって異なります。 Microsoft が SOA 実装の多数の実例から得た経験に基づいて、ESB を次のように考えることができます。つまり、ESB は、従来のエンタープライズ アプリケーション統合 (EAI)、メッセージ指向ミドルウェア、Web サービス、.NET と Java の相互運用性、ホスト システム統合、サービス レジストリおよび資産リポジトリとの相互運用性をベースとするアーキテクチャ パターンのコレクションです。  
  
## <a name="audience-requirements"></a>利用者の要件  
 BizTalk ESB Toolkit は、Microsoft BizTalk Server ソリューション、または BizTalk ESB Toolkit コンポーネントを使用した他のソリューションを作成する開発者向けです。 BizTalk ESB Toolkit を最大限に活用するには、開発者には以下に関する知識と経験が必要です。  
  
1.  Microsoft BizTalk Server  
  
2.  Microsoft Visual Studio  
  
3.  Microsoft .NET 開発手法 (ASP.NET Web サービスおよび .NET Framework コンポーネントの開発など)  
  
## <a name="how-the-biztalk-esb-toolkit-works"></a>BizTalk ESB Toolkit の動作  
 BizTalk ESB Toolkit は、受信メッセージを受け取り、受け取ったメッセージに対して操作を実行します。その際、通常 (必ずではない) は、変換や配信などのプロセスまたはその他のカスタム定義プロセスを実行します。 必要な操作を指定するには、中心となる処理コンポーネントに、関連付けられた指示またはメタデータを格納するメッセージが必要です。その指示またはメタデータにより、メッセージの内容に対して適用するプロセスおよび実行するタスクが定義されます。   
これにより、サービスの間の疎結合これは、ESB メッセージごとに、特定の処理に関する予備知識が必要ないことを意味します。 ESB に必要な情報は、発生する可能性のあるプロセスの範囲と、各プロセスを適用する方法だけです。 使用可能なプロセスおよびプロセスと指示のマッピングをメッセージ内に指定するための広範囲なオプションが用意されているので、コードの変更やコンポーネントの再展開を必要とせずに動作を構成および調整するための柔軟なメカニズムが実現されています。  
  
## <a name="getting-started"></a>作業の開始  
 BizTalk ESB Toolkit をインストールすると、「はじめに」のトピックを読む必要があります、 [BizTalk ESB Toolkit のドキュメント](http://go.microsoft.com/fwlink/?LinkId=193578) 、アーキテクチャ、メッセージ フローを BizTalk ESB Toolkit のコア コンポーネントを理解します。 また、BizTalk ESB Toolkit に付属するサンプルをインストールして実行することをお勧めします。サンプルには、「はじめに」のトピックや他のメッセージング シナリオで説明している一般的な使用例が示されています。 このアプローチにより、BizTalk ESB Toolkit が動作するしくみと、ユーザー独自の SOA アプリケーションで BizTalk ESB Toolkit の機能を活用する方法を短時間で把握できます。  
  
## <a name="see-also"></a>参照  
 [BizTalk エンタープライズ サービスのガイダンス](http://go.microsoft.com/fwlink/?LinkId=193577)   
 [サービス指向ソリューション](../core/service-oriented-solution.md)   
 [Web サービスの使用](../core/using-web-services.md)