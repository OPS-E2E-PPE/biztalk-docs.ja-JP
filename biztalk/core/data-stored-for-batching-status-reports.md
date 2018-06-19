---
title: データが格納されているバッチの状態レポートの |Microsoft ドキュメント
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
ms.openlocfilehash: db9831aafce56845fe7b75e91f5369a8860d8996
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238594"
---
# <a name="data-stored-for-batching-status-reports"></a>バッチの状態レポート用に格納されるデータ
ときに、**レポートをオンに**、アグリーメントのプロパティが選択されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は各バッチ処理のインスタンスの状態を格納します。 このプロパティで使用できる、**全般プロパティ**のページ、**全般** タブで、**アグリーメントのプロパティ** ダイアログ ボックス。 状態は、次のいずれかの値になります。  
  
-   **定義されている**: バッチ インスタンスは、構成します。 バッチ アクティベーションの開始日時は、現在の日時よりも後になっています。 バッチ パラメーターはすべて定義されていますが、バッチは実行されていません (ドキュメントを受理していません)。  
  
-   **アクティブな**: バッチ インスタンスはアクティブ化されており、トランザクション セットを集計しています。 受理/拒否されたトランザクション セットの数を表示できます。  
  
-   **リリース**: バッチ リリース条件を満たすと、メッセージ ボックスにリリースされましたが、送信パイプラインによってリリースされていないか、すべてのメッセージを処理する前に、バッチが停止しました。  
  
-   **完了**: バッチは EdiSend パイプラインによって送信されました。  
  
 バッチが EdiSend パイプラインによって送信されると、UI にあるバッチ レコードを、送信された EDI インターチェンジのレコードに関連付けて、トランザクション セットの詳細を参照できます。  
  
> [!NOTE]
>  "完了" 状態のバッチ インスタンスは、1 つのバッチ構成について複数存在することが可能です。  
  
 **バッチ インターチェンジの関連付け**  
  
 BusinessMessageJournal BAM アクティビティにより、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、トランザクション セットを持つ受信 EDI インターチェンジを、同じトランザクション セットを持つ送信バッチ インターチェンジと関連付けることができます。 実装してこの相関関係情報を使用する方法については、次を参照してください。[送信バッチで受信トランザクション セットを相互に関連付ける](../core/correlating-an-incoming-transaction-set-with-an-outgoing-batch.md)です。  
  
## <a name="see-also"></a>参照  
 [格納されている EDI および AS2 状態レポートのデータ](../core/data-stored-for-edi-and-as2-status-reports.md)   
 [EDI 状態レポートに格納されているデータ](../core/data-stored-for-edi-status-reports.md)   
 [AS2 状態レポートに格納されているデータ](../core/data-stored-for-as2-status-reports.md)