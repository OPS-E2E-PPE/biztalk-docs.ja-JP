---
title: 機能テストの実行 |Microsoft Docs
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
ms.openlocfilehash: e0f1736ddc0956de470ebdc1f3f1a6adaa2f8f94
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291340"
---
# <a name="performing-functional-testing"></a>機能テストの実行
機能テストを使用する特定の BizTalk アプリケーションのコンテキストで特定のエンド ツー エンド シナリオまたは特定のユース ケースをテストします。 機能テストには、障害のパスを含む、特定のシナリオのすべての可能なパスがについて説明します。 アプリケーションが適切に処理エラーの条件を使用することを確認するエラー パスを評価する必要があります。  
  
 すべてのアイテム (オーケストレーション、カスタム パイプライン コンポーネントでは、カスタム アセンブリなど) を呼び出す必要があるし、もこれらのオブジェクトのすべてのコード分岐をテストする必要があります。 メッセージがシステムを正しくフローすることを確認するメッセージの有効なすべての組み合わせを行う必要があります。 無効なメッセージは、エラーが発生した場合、予想される方法で、アプリケーションが反応するかどうかを確認し、オーケストレーションおよびカスタム コンポーネントのすべての例外ブロックに含まれるコードをテストするもテストする必要があります。  
  
## <a name="automating-functional-testing"></a>機能テストの自動化  
 繰り返せることから、ようにし、人的エラーを回避されますが、高速にするように、機能テストを自動化する必要があります。 **BizUnit**デザイン迅速にテスト_ケースを開発者向けに設計された宣言型のテスト フレームワークです。 実際には、XML のための BizUnit テスト_ケースと呼ばれる XML 構成ファイルでは、テストを実行する方法を定義するだけです。 テストを実行する独自のカスタム ドライバーを作成することも簡単にご利用の詳細は**Visual Studio Unit Testing**または**NUnit**をホストし、テストを実行します。  
  
 すべての XML のための BizUnit テスト_ケースには、3 つのフェーズが含まれています。**TestSetup**、 **TestExecution**、および**TestCleanup**します。 これらの各フェーズは、0 個以上のテスト ステップを含めることができます。 各ステップは、作業単位を表し、特定のタスクを実行するように .NET クラスとして実装されます。 このフレームワークは、コンポーネントの豊富なセットを提供します。 ただし、特定の要件を満たすために特殊化されたコンポーネントを理解する必要がある場合、独自のカスタムのテスト手順コンポーネント記述できます。 これらのツールの詳細については、次を参照してください。[テスト用ツール](~/technical-guides/tools-for-testing.md)します。  
  
> [!NOTE]  
>  、Microsoft では、このツールの使用はサポートされていないと、Microsoft はこのプログラムの適合性に関する保証をいたしません。 このプログラムは、ユーザー自身の責任で使用してください。  
  
## <a name="see-also"></a>参照  
 [チェックリスト:運用準備のテスト](../technical-guides/checklist-testing-operational-readiness.md)