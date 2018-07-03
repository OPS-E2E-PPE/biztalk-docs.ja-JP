---
title: ビジネス ルール フレームワークのアーキテクチャ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rules Framework, caching
- Business Rules Framework, Rule Engine Update service
- rule store [Business Rules Framework]
- Policy class [Business Rules Engine]
- Business Rules Framework, architecture
- Business Rules Framework, RuleEngine class
- Business Rules Framework, Policy class
- Business Rules Framework, authoring tools
- RuleEngine class [Business Rules Engine]
- caching, Business Rules Framework
- Business Rules Framework, fact retrievers
- architecture, Business Rules Framework
- Business Rules Framework, rule store
ms.assetid: f5570cca-7664-4180-af9c-64ef90a0022b
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f55c624f8eaac517d11774ec2c542bf4ddbe0351
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971843"
---
# <a name="business-rules-framework-architecture"></a>ビジネス ルール フレームワークのアーキテクチャ
次の図に、ビジネス ルール フレームワークのコンポーネント アーキテクチャを示します。  
  
 ![ビジネス ルール フレームワーク コンポーネント アーキテクチャ](../core/media/ebiz-rulesarch-new.gif "ebiz_rulesarch_new")  
Microsoft ビジネス ルール フレームワークのアーキテクチャ  
  
 ここでは、このフレームワークの一部のコンポーネントについて説明します。  
  
## <a name="policy-class"></a>Policy クラス  
 A**ポリシー**オブジェクトは、ビジネス ポリシーの 1 つのインスタンスと、ルール ベースのアプリケーションで使用されるインターフェイスを提供します。 このオブジェクトで提供される抽象化により、ルール ストアの場所をアプリケーション開発者が配慮する必要がなくなり、ルール ストアからのルール セットの抽出、基になるルール エンジンのインスタンスのインスタンス化、長期間のファクトのエンジンへのアサートが可能になります。 ルール ベースのアプリケーションを多くのシナリオでの同時実行のインスタンスを使用して、**ポリシー**オブジェクト。 これらの同時インスタンスでは、同一ポリシーを表すことも、同一ポリシーの複数バージョンを表すことも、異種ポリシーの複数バージョンを表すこともあります。  
  
## <a name="ruleengine-class"></a>RuleEngine クラス  
 **RuleEngine**オブジェクトは、ビジネス ポリシーの実行エンジンとして機能します。 このオブジェクトは、3 つのプラグイン コンポーネント (変換者、推論エンジン、および追跡インターセプター) を実装に使用します。 A **RuleEngine**オブジェクトは、 **RuleSet**入力として、ビジネス ポリシーを表すオブジェクト、トランスレーター、推論エンジン、および追跡インターセプターの実装時に設定するルールの構成を使用して、ルール セットによって定義されたビジネス ポリシー。  
  
## <a name="fact-retriever"></a>ファクト取得コンポーネント  
 ファクト取得コンポーネントは、ユーザーによって定義される省略可能なプラグイン コンポーネントであり、ビジネス ポリシーによって使用される長期間のファクトを収集します。 詳細については、次を参照してください。[ファクト取得コンポーネントを作成する方法](../core/how-to-create-a-fact-retriever.md)します。  
  
 実行前に、**ポリシー**オブジェクトのインスタンスが提供、 **RuleEngine**一連のルール エンジン内のファクトを更新する機会を与えます、ファクト取得コンポーネントのインスタンスの作業メモリ。 詳細については、次を参照してください。[の短期的なファクトとします。長期間のファクト](../core/short-term-facts-vs-long-term-facts.md)します。  
  
## <a name="rule-engine-update-service"></a>ルール エンジン更新サービス  
 ルール エンジン更新サービスは、分散環境でビジネス ポリシーの動的な更新を可能にします。 自動的に起動する Microsoft Windows NT サービスのアプリケーションでは、ビジネス ポリシーが変更された場合に発生するポリシー展開イベントと展開解除イベントをサブスクライブする必要があります。  
  
 一般的な企業シナリオでは、ビジネス ポリシーの展開は、更新、テスト、およびバージョン管理の後で行われます。 展開とは、更新されたポリシーをセキュリティで保護された永続的なルール ストアに追加して、必要に応じてストアに対してロジックを実行し、更新されたポリシーに関する情報をすべての関係者に公開することを指します (公開されるのはポリシー自体ではなく、ポリシーに関する情報です)。  
  
 ルール ベース アプリケーションのホスト サーバーで実行されるルール エンジン更新サービスは、ポリシー更新通知を受信し、これらの情報を後で使用できるようにキャッシュします。 ポリシーの更新に公開/サブスクライブ モデルを使用すると、サービスのダウンタイムまたは中断を生じることなく、ビジネス ポリシーをほぼリアルタイムで変更できます。  
  
## <a name="policyvocabulary-authoring-tools"></a>ポリシー/ボキャブラリ作成ツール  
 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のビジネス ルール作成ツールには、ポリシーやボキャブラリを作成するためのエンド ユーザー向け機能と開発者向け機能が両方備わっています。  
  
## <a name="rule-store"></a>ルール ストア  
 A*ルール ストア*はビジネス ポリシーおよびボキャブラリのリポジトリです。 このリポジトリは、簡単なファイルである場合も、安全性、拡張性、持続性、および信頼性の高い Microsoft SQL Server などのデータベースである場合もあります  (SQL Server は、既定ルールのストアとして使用フレームワーク)。  
  
## <a name="caching"></a>キャッシュ  
 ビジネス ルール エンジン フレームワークは、キャッシュ メカニズムを提供します。 **RuleEngine**インスタンス。 各**RuleEngine**インスタンスには、特定のポリシーのバージョンのメモリ内表現が含まれています。  
  
 次の手順では、新しいプロセス**ポリシー**インスタンスがインスタンス化 (いずれかの実行または API の呼び出しで、**ルールの呼び出し**図形)。  
  
1. **ポリシー**要求オブジェクト、 **RuleEngine**ルール エンジン キャッシュからのインスタンス。  
  
2. 場合、 **RuleEngine** 、キャッシュに存在するポリシーのバージョンのインスタンス、 **RuleEngine**にインスタンスが返されます、**ポリシー**オブジェクト。 場合、 **RuleEngine**インスタンスが利用できない、キャッシュは、新しいインスタンスを作成します。 ときに、 **RuleEngine**インスタンスがインスタンス化されますが、さらに、これは、ポリシーのバージョンのいずれかが構成されている場合は、新しいファクト取得コンポーネントのインスタンスを作成します。  
  
   ときに、 **Execute**でメソッドが呼び出される、**ポリシー**オブジェクトを次の手順が発生します。  
  
3. ポリシー オブジェクトの呼び出し、 **UpdateFacts**ファクト取得コンポーネントが存在する場合は、ファクト取得コンポーネントのインスタンス上のメソッド。 メソッドのファクト取得コンポーネントの実装の作業メモリに長期間のファクトをアサートすることがあります、 **RuleEngine**します。  
  
4. **ポリシー**オブジェクトに含まれている短期間のファクトをアサートする、**配列**で渡された、 **Execute**呼び出します。  
  
5. **ポリシー**オブジェクト呼び出し**Execute**上、 **RuleEngine**します。  
  
6. **RuleEngine**実行が完了して、制御を戻します、**ポリシー**オブジェクト。  
  
7. **ポリシー**オブジェクトはから短期間のファクトを取り消します、 **RuleEngine**します。 ファクト取得コンポーネントによってアサートされた長期間のファクトは、ルール エンジンの作業メモリに残ります。  
  
   後に、 **Dispose**メソッドが、**ポリシー**オブジェクト、 **RuleEngine**にルール エンジンのキャッシュ インスタンスを解放します。  
  
   ルール エンジンのキャッシュは、読み込みで必要な場合、特定のポリシー バージョンに関して複数のルール エンジン インスタンスを保持し、各ルール エンジン インスタンスはそれぞれ独自のファクト取得コンポーネント インスタンスを保持します。  
  
## <a name="see-also"></a>参照  
 [ビジネス ルール エンジン](../core/business-rules-engine.md)