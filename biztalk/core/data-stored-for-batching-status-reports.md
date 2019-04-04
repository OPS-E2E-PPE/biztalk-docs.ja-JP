---
title: データが格納されているバッチの状態レポートの |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d55aa0e1-095f-434e-8530-f1a946ad4430
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f42d503177e3b00ce418913e66948eb813575ab1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006859"
---
# <a name="data-stored-for-batching-status-reports"></a>バッチの状態レポート用に格納されるデータ
ときに、**レポートを有効にする**、アグリーメントのプロパティが選択されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]バッチ処理の各インスタンスの状態に格納されます。 このプロパティはで使用できる、**全般プロパティ**のページ、**全般** タブで、**アグリーメントのプロパティ** ダイアログ ボックス。 状態は、次のいずれかの値になります。  
  
- **定義されている**: バッチ インスタンスが構成されています。 バッチ アクティベーションの開始日時は、現在の日時よりも後になっています。 バッチ パラメーターはすべて定義されていますが、バッチは実行されていません (ドキュメントを受理していません)。  
  
- **アクティブな**: バッチ インスタンスがアクティブ化されて、トランザクション セットを集計します。 受理/拒否されたトランザクション セットの数を表示できます。  
  
- **リリース**: バッチ リリース条件を満たす、メッセージ ボックスにリリースされていますが、送信パイプラインによってリリースされていない、またはすべてのメッセージを処理する前に、バッチが停止しました。  
  
- **完了した**: バッチは EdiSend パイプラインによって送信されました。  
  
  バッチが EdiSend パイプラインによって送信されると、UI にあるバッチ レコードを、送信された EDI インターチェンジのレコードに関連付けて、トランザクション セットの詳細を参照できます。  
  
> [!NOTE]
>  "完了" 状態のバッチ インスタンスは、1 つのバッチ構成について複数存在することが可能です。  
  
 **バッチ インターチェンジの関連付け**  
  
 BusinessMessageJournal BAM アクティビティにより、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、トランザクション セットを持つ受信 EDI インターチェンジを、同じトランザクション セットを持つ送信バッチ インターチェンジと関連付けることができます。 実装して、この相関関係情報を使用する方法については、[送信バッチで受信トランザクション セットの関連付け](../core/correlating-an-incoming-transaction-set-with-an-outgoing-batch.md)を参照してください。  
  
## <a name="see-also"></a>参照  
 [EDI および AS2 状態レポートの格納データ](../core/data-stored-for-edi-and-as2-status-reports.md)   
 [EDI 状態レポート用に格納されているデータ](../core/data-stored-for-edi-status-reports.md)   
 [AS2 状態レポート用に格納されるデータ](../core/data-stored-for-as2-status-reports.md)