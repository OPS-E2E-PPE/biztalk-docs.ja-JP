---
title: 'パターンを使用したデザイン: ビジネス プロセス管理ソリューション |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- patterns [process management solutions], examples
- patterns [process management solutions], designing
- examples, programming patterns
- designing, programming patterns
ms.assetid: 0583f4a4-01db-4d5b-a1f5-1694c1ddbd30
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91da8c63fc46ee90696e257bfd6142b5088af305
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239666"
---
# <a name="designing-with-patterns-the-business-process-management-solution"></a>パターンを使用したデザイン: ビジネス プロセス管理ソリューション
ビジネス プロセス管理ソリューションは、BizTalk アプリケーションでプロセス マネージャを構築する方法の 1 つです。 このソリューションでは、1 つのコンポーネントを使用して、注文処理に含まれる一連のステージを選択および制御します。 ソリューションが注文を取得: 新しいサービス、変更、またはサービスの取り消しがあります:、ログに記録し、処理のため渡す前に、順序を確認します。 注文処理は、注文を扱う 1 つ以上のステージで構成されます。 処理が終わったら、元の注文要求に最後の応答を返します。  
  
 適切に設計されたプロセス管理ソリューションを使用すると、残りのアプリケーションを再構築することなく、プロセスに対するステージの追加や削除を行うことができます。 このソリューションでは、このアプローチを考慮しています。 発注プロセスは、分離した個別のステージに分割されます。 すべてのステージは、同じポートから読み込み、フィルタを使用して処理するメッセージを決定します。 この詳細は、次のセクション「パターン」に記載されています。  
  
 このソリューションは、Web サービスを通じた入力も受け付けます。ただし、FTP 接続を使用して、サービス以外のインターフェイスもこのソリューションで使用できます。 この機能は、バッチ システムでアプリケーションを使用する方法をシミュレートします。  
  
## <a name="patterns"></a>パターン  
 次の図は、前のセクションで説明したビジネス プロセス管理ソリューションのパターンを簡略化して示しています。  
  
 ![ビジネス プロセス管理ソリューション パターン](../core/media/bts-cp-business-process-management-patterns.gif "bts_cp_Business_Process_Management_Patterns")  
  
 このソリューションは、サービス インターフェイス、FTP チャネル、さまざまなトランスレータ、プロセス マネージャ、および 2 つの処理ステージで構成されます。 処理前のセクションにおける 4 つのトランスレータは、サービス インターフェイスに戻る受信確認メッセージを作成し、履歴データベースまたは追跡データベースのエントリを生成し、サービス システムのエントリを作成します。 4 つ目のトランスレータは、プロセス マネージャが必要とするメッセージを作成します。 次に、プロセス マネージャは、処理ステージを制御します。  
  
 プロセス マネージャの多くの実装で、マネージャは、処理状態を追跡します。 図で示されているように、この実装は、これを変更します。 このソリューションを使用すると、プロセス マネージャは、メッセージにフラグを設定して、メッセージを次に処理する処理ステージを指定します。 次に、各ステージは、フィルタを使用して、特定のメッセージを処理するかどうかを決めます。  
  
 この手法では、プロセス マネージャがルーティング情報を保存する必要がありません。 マネージャとさまざまなステージ間のすべてのメッセージは、同じポートを使用します。 ステージを追加する場合、適切なポートでの送受信と正しいステージ番号のフィルタ処理を行うコンポーネントを追加するだけです。 プロセス マネージャの設定を変更する必要はありません。  
  
 多くのことが図から省略されていることに注意してください。 処理ステージが — し、実際には、操作を行います: バックエンド プロセスと通信します。 このソリューションは、プロセスの複数の場所で履歴情報も収集できます。 最も重要な点として、プロセス マネージャのロジックが示されていません。 また、同期接続および非同期接続の使用状況も示されていません。 これらは、次のセクションで扱います。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションのパターン](../core/patterns-in-the-business-process-management-solution.md)   
 [ビジネス プロセス管理ソリューションのパターンの変換](../core/translating-the-patterns-of-the-business-process-management-solution.md)