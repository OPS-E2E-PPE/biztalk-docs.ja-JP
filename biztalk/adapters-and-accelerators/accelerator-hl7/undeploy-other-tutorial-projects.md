---
title: "その他のチュートリアルのプロジェクトを展開解除 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5fce837f-1853-4d5d-a680-8ae2a974c750
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e5c4d7e20fc4d8e7c8bea724625dde770b4aca2
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="undeploy-other-tutorial-projects"></a>その他のチュートリアルのプロジェクトを展開解除します。
BizTalk Accelerator 用 HL7 に展開するときに ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) チュートリアル、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]チュートリアルのアセンブリ ファイル、構成データベース (BizTalk 管理データベースとも呼ばれます) と、グローバル アセンブリ キャッシュに格納します。 別に実行している場合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]チュートリアル、および展開されたそのチュートリアルで作成したアセンブリときに、発生するエラー、バッチ処理のチュートリアルの 3 つの部分でアセンブリをテストします。 1 つのメッセージ スキーマを一度に 1 つのみ展開できます可能性があります。  
  
 前のチュートリアルに展開されたアセンブリを展開解除によってこれらのエラーを回避できます。 必要な場合は、後でアセンブリを再配置することができます。  
  
 アセンブリを展開解除する前に、アセンブリ内のオーケストレーションを参加解除する必要があります。 また、展開されたままにする他のアセンブリから、展開を解除するアセンブリへの参照を削除する必要があります。 代わりに別のチュートリアルを開始する前に、1 つのチュートリアルに関連付けられているすべての Dll の削除を開始します。  
  
### <a name="to-undeploy-an-assembly"></a>アセンブリを展開解除するには  
  
1.  Visual Studio での BizTalk エクスプ ローラーでオーケストレーションをクリックし、をクリックして展開解除するアセンブリで使用するオーケストレーションを参加解除**参加解除**です。  
  
2.  展開されたままにする任意のアセンブリでは、展開解除するアセンブリへの参照を削除します。 ソリューション エクスプ ローラー内の参照を右クリックし、をクリックして**削除**です。  
  
3.  BizTalk エクスプ ローラーを開きの展開を解除し、をクリックするアセンブリを右クリックして**Undeploy**です。  
  
 アセンブリの展開解除の詳細については、「展開解除するアセンブリを使用して BizTalk エクスプ ローラー」BizTalk Server ヘルプを参照してください。  
  
## <a name="see-also"></a>参照  
 [バッチ処理のチュートリアルを使用するための準備](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-batching-tutorial.md)