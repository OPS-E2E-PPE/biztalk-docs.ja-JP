---
title: 失われた追跡データの特定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data loss, HAT
- reporting tools
- Orchestration Debugger
- Tracking database, data loss
- HAT, data loss
- HAT, Operation View tool
- HAT, reporting tools
- Operation View tool, MessageBox database
- MessageBox database, Operation View tool
- Operation View tool, data loss
ms.assetid: 1ac13e2c-cd5e-437e-b924-d4547931874e
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01290e6bec1157baed8bbb89d73b10a904dc1250
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332533"
---
# <a name="identifying-lost-tracking-data"></a>失われた追跡データの特定
追跡データが、ハードウェア障害の結果として失われたかを識別できるように、BizTalk Server 管理コンソールを使用することができます。 BizTalk Server 管理コンソールを使用して、ライブまたはアーカイブ済みのデータのことができます。  
  
 BizTalk Server 管理コンソールを使用すると、どのサービスがメッセージ ボックス データベースの回復時にアクティブだったかを判断します。 データベースが回復された時間とハードウェア障害の発生時の間にギャップがあるために、一部のトランザクションの状態を確認することはできません。  
  
 完了し、次のように、復旧ポイントの後に起動するサービス インスタンスを識別するために、追跡データを使用できます。  
  
- データベースをバックアップするインスタンスが完了したか、前回の開始を探します。  
  
- BizTalk 追跡 (BizTalkDTADb) データベース内のデータには、データベースにメッセージがないことと、メッセージの開始が完了しませんでしたが示されている場合、そのメッセージは、前回のバックアップ後に送信されました。  
  
  追跡が完了すると、任意のサービスをレポートことができ、サービスが開始されていることを示すことができます。 追跡データはまずメッセージ ボックスにステージングし、その後、BizTalk 追跡データベースに移動します。 ステージングされたデータを BAM イベント バス サービスのバックログが失われたされている可能性があります。  
  
  すべてのデータベースでは、運用上の理由から、同じマークに復元するのに必要がありますが、記号の後の変更点を確認するのにアーカイブのモードで (ですが、失われなかった BizTalk 追跡データベースを使用することができます。  
  
  追跡が完了済みのサービス インスタンスが表示される場合は、そのインスタンスを終了できます。 これにより、復旧ポイント以降に開始されたインスタンスが表示されます。 そのため、これらのインスタンスがすべてのアクションを補正し、初期アクティベーション メッセージを再送信する必要がある場合。  
  
  オーケストレーション デバッガーを使用すると、実行、およびメッセージ フローが送信または受信メッセージがする必要がありますを使用する最後の図形を参照してください。  
  
  BizTalk 追跡データベースが失われた、過去の復旧ポイントの変更点のすべての検出は、外部システムのレポート メカニズムを使用して行う必要があります。  
  
## <a name="see-also"></a>参照  
 [データ損失の解決](../core/resolving-data-loss.md)