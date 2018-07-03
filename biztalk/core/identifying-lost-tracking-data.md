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
ms.openlocfilehash: 17116d3a560e968e8dd9da0e42f5af221c23f5d3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982859"
---
# <a name="identifying-lost-tracking-data"></a>失われた追跡データの特定
BizTalk Server 管理コンソールを使用することによって、ハードウェア障害の結果として、どの追跡データが失われたかを特定できます。 BizTalk Server 管理コンソールは、ライブ データまたはアーカイブ済みデータについて使用できます。  
  
 BizTalk Server 管理コンソールを使用すると、どのサービスがメッセージ ボックス データベースの回復時にアクティブだったかを判断します。 データベースの復旧時点とハードウェア障害の発生時点の間には時間差があるため、一部のトランザクションの状態を特定できない場合があります。  
  
 完了済みのサービス インスタンスや、復旧ポイント以降に開始されたサービス インスタンスを特定するには、追跡データを次のように使用します。  
  
- データベースの前回バックアップ時以降に完了または開始されたインスタンスを探します。  
  
- BizTalk 追跡 (BizTalkDTADb) データベースのデータを見て、開始されているにもかかわらず完了していないメッセージがあった場合、そのメッセージがデータベースに存在しなければ、前回のバックアップ後に送信されたメッセージであると判断できます。  
  
  追跡からは、完了したすべてのサービスに加え、開始済みのサービスが報告されることもあります。 追跡データは、まずメッセージ ボックスにステージングされ、その後、BizTalk 追跡データベースに移動されます。 ステージングされたデータは、BAM イベント バス サービスのバックログに紛れ込んでいる可能性があります。  
  
  運用上必要な操作は、すべてのデータベースを同じマークまで復元することですが、失われなかった BizTalk 追跡データベースをアーカイブ モードで使用して、マーク以降の動きを確認することもできます。  
  
  追跡によってサービス インスタンスが完了済みであることがわかれば、そのインスタンスを強制終了できます。 追跡では、復旧ポイント以降に開始されたインスタンスが示される場合もあります。 その場合は、該当するインスタンスによって行われたアクションに関する補正を行ってから、初期アクティベーション メッセージを再送信する必要があります。  
  
  オーケストレーション デバッガーを使用すると、最後に実行された図形を特定し、本来、送受信されるべきであったメッセージを、メッセージ フローを使って確認できます。  
  
  BizTalk 追跡データベースが失われた場合、復旧ポイント後の動きはすべて、外部システムのレポート メカニズムを使って調べる必要があります。  
  
## <a name="see-also"></a>参照  
 [データ損失の解決](../core/resolving-data-loss.md)