---
title: 機能テストを実行して |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b9c8c95-5a25-4255-a4c2-e26c67b7a620
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f17c2701d6aa90393b8839bafc933bea2fba5746
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302322"
---
# <a name="performing-functional-testing"></a>機能テストを実行します。
テストを使用する機能を特定の BizTalk アプリケーションのコンテキストで、特定のエンド ツー エンド シナリオまたは特定のユース ケースをテストします。 機能テストには、エラーのパスを含む特定のシナリオのすべての可能なパスを取り扱う必要があります。 エラー パスを評価して、アプリケーションが適切に処理エラー条件のことを確認する必要があります。  
  
 (オーケストレーション、カスタム パイプライン コンポーネントのカスタム アセンブリなど) のすべての成果物を呼び出す必要があります、およびこれらのオブジェクトのすべてのコード分岐をもテストする必要があります。 メッセージがシステムを通じて正しくフローすることを確認するメッセージのすべての可能な組み合わせを実行する必要があります。 無効なメッセージは、アプリケーションがエラーが発生した場合、予想される方法で動作することを確認し、オーケストレーションおよびカスタム コンポーネントのすべての例外ブロックに含まれるコードをテストするもテストする必要があります。  
  
## <a name="automating-functional-testing"></a>機能テストの自動化  
 高速繰り返せることから、ようにヒューマン エラーを回避することができるようにするように、機能テストを自動化する必要があります。 **BizUnit**宣言型テスト フレームワークを開発者がデザイン急速にテスト_ケースを有効にするよう設計されています。 実際には、BizUnit XML テスト_ケースと呼ばれる XML 構成ファイルでは、テストを実行する方法を定義するだけです。 テストを実行する独自のカスタム ドライバーを作成することも簡単に活用詳細**Visual Studio 単体テスト**または**NUnit**ホストし、テストを実行します。  
  
 BizUnit XML のすべてのテスト_ケースには、3 つのフェーズが含まれています: **TestSetup**、 **TestExecution**、および**TestCleanup**です。 これらの各フェーズにより、0 個以上のテスト ステップが含めることができます。 各手順では、作業の単位を表し、特定のタスクを実行するように .NET クラスとして実装します。 このフレームワークは、コンポーネントの機能豊富なセットを提供します。 ただしを特定の要件を満たすために特別なコンポーネントを実現する必要がある場合は、独自のカスタムのテスト ステップ コンポーネントを記述することができます。 これらのツールの詳細については、次を参照してください。[テスト用ツール](~/technical-guides/tools-for-testing.md)です。  
  
> [!NOTE]  
>  、Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関して保証を行いません。 このプログラムは、ユーザー自身の責任で使用してください。  
  
## <a name="see-also"></a>参照  
 [チェックリスト: テスト運用の準備](../technical-guides/checklist-testing-operational-readiness.md)