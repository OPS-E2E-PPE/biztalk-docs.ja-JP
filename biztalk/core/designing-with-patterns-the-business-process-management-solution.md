---
title: 'パターンと設計: ビジネス プロセス管理ソリューション |Microsoft Docs'
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
ms.openlocfilehash: 4b3477ff868c6a5f07d6a600e35c1dea4b3d6cf9
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530935"
---
# <a name="designing-with-patterns-the-business-process-management-solution"></a>パターンと設計: ビジネス プロセス管理ソリューション
ビジネス プロセス管理ソリューションは、BizTalk アプリケーションでプロセス マネージャを構築する方法を示しています。 ソリューションを選択し、注文処理ステージの順序を制御するコンポーネントを使用します。 ソリューションが注文を取得: 新しいサービス、変更、またはサービスのキャンセルになる可能性があるなど、ログに記録し、処理のため渡す前に、順序を確認します。 処理は、注文を処理する 1 つまたは複数のステージで構成されます。 最後に、ソリューションは、元の注文要求に最後の応答を返します。  
  
 適切に設計されたプロセス管理ソリューションでは、アプリケーションの残りの部分を再構築することがなく、プロセスからステージを増減することができます。 このソリューションで使用される手法ではまさに、します。 注文処理は、離散、独立したステージに分割されます。 すべてのステージでは、同じポートから読み取られ、フィルターを使用するメッセージが処理するかを判断します。 これについては詳しく説明では、次のセクションでは、「パターンです」。  
  
 このソリューションでは、このソリューションで、FTP 接続サービス以外のインターフェイスを使用することもできますが、Web サービスを通じての入力も受け付けます。 この機能は、バッチ システムでアプリケーションを使用する方法をシミュレートします。  
  
## <a name="patterns"></a>パターン  
 次の図は、前のセクションで説明したビジネス プロセス管理ソリューションでパターンの簡略化されたバージョンを示します。  
  
 ![ビジネス プロセス管理ソリューション パターン](../core/media/bts-cp-business-process-management-patterns.gif "bts_cp_Business_Process_Management_Patterns")  
  
 ソリューションは、次の部分で構成されます: サービス インターフェイス、FTP チャネル、さまざまなトランスレータ、プロセス マネージャ、および 2 つの処理ステージ。 処理前のセクションでは、4 つのトランスレータは、サービス インターフェイスに戻るには、履歴または追跡データベースにエントリを生成し、サービス システムにエントリを作成する受信確認メッセージを作成します。 4 番目のトランスレーターは、プロセス マネージャーによって必要とするメッセージを作成します。 さらに、プロセス マネージャーは、処理ステージを制御します。  
  
 多くのプロセス マネージャーの実装では、マネージャーは、処理状態を追跡します。 この実装では、図が示すようにこれを変更します。 このソリューションでは、プロセス マネージャーは、メッセージを次に処理する処理ステージを示すメッセージのフラグを設定します。 各ステージは、このフィルターを使用して、特定のメッセージを処理する必要があるかどうかを決定します。  
  
 このアプローチを使用して、ルーティング情報を維持するために、プロセス マネージャがありません。 マネージャとさまざまなステージ間のすべてのメッセージは、同じポートを使用します。 ステージを追加するには、のみを送信し、適切なポートと正しいステージ番号のフィルターが受信するコンポーネントを追加する必要があります。 プロセス マネージャー自体で何も変更する必要はありません。  
  
 図から多くを省略することに注意してください。 処理ステージ月- し、操作を実際には、-バックエンド プロセスと通信します。 ソリューションでは、プロセスの 1 つ以上の時点で履歴情報も収集できます。 おそらく、最も重要な点は、プロセス マネージャのロジックが指定されていません。 さらに、同期または非同期接続の使用が指定されていません。 これらは、次のセクションで検討されます。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションのパターン](../core/patterns-in-the-business-process-management-solution.md)   
 [ビジネス プロセス管理ソリューションのパターンの変換](../core/translating-the-patterns-of-the-business-process-management-solution.md)