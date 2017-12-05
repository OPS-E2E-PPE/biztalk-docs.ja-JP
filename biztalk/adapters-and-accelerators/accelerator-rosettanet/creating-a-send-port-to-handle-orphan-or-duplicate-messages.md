---
title: "孤立したメッセージまたは重複メッセージを処理する送信ポートの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, duplicate messages
- messages, orphaned messages
- send ports, duplicate messages
- send ports, orphaned messages
- messages, send ports
ms.assetid: 61d51206-13e3-4d32-a184-866248db9b45
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fc969e316df9b493dd294769d68a15012a46904
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="creating-a-send-port-to-handle-orphan-or-duplicate-messages"></a>孤立したメッセージまたは重複メッセージを処理する送信ポートの作成
ここでは、孤立したメッセージや重複メッセージの削除に使用できる送信ポートの設定方法について説明します。  
  
 孤立したメッセージまたは重複するメッセージが問題になる[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]パブリック プロセス オーケストレーションのメッセージの最初のコピー処理が完了した後、メッセージの追加のコピーを受信します。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]これらのメッセージを重複としてマークし、それらを中断します。 これらのメッセージは BizTalk 管理コンソールに表示できます。 BizTalk 管理コンソールの詳細については、「を使用して、BizTalk 管理コンソール」で、BizTalk Server ヘルプを参照してください。  
  
 孤立したメッセージまたは重複メッセージは、それらを再表示または削除するまで BizTalk 管理コンソールに残ります。 これらのメッセージを削除する最も効果的な方法は、孤立したメッセージまたは重複メッセージのフィルターを設定した送信ポートを設定することです。 BizTalk Server で使用可能な輸送手段を使用してそれらの操作を行うことができます。 たとえば、ファイル トランスポートを使用して、移動できます。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]ハード_ディスク上の場所にファイルとして、孤立したメッセージまたは重複メッセージを送信します。 これにより、それらを簡単に削除できます。 ポートは、参加している状態の場合も停止状態の場合もありますが、停止状態では、そのポートに送信されたすべてのメッセージは、その送信ポートの下に保留メッセージとして表示されます。  
  
> [!NOTE]
>  重複/孤立したメッセージを処理する送信ポートを作成する代わりに、特別なパイプライン コンポーネントを作成して、MessageBox データベースからそれらのメッセージを削除できます。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] SDK の FixMsg コンポーネントをテンプレートとして使用できます。 `IComponent.Execute` メソッドが Null を返すように変更する必要があります。 これにより、パイプラインに送られたメッセージでこのコンポーネントを含むものが [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] で破棄されます。 このパイプライン コンポーネントは、コンパイルして送信パイプラインに追加し、その後、シンク ポートの送信パイプラインをコンパイルし、展開し、選択します。 詳細については、次を参照してください。"CustomComponent ([!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]サンプル)"BizTalk Server のヘルプ。  
  
### <a name="to-create-a-send-port-to-handle-orphan-or-duplicate-messages"></a>孤立したメッセージまたは重複メッセージを処理する送信ポートを作成するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の**ビュー** メニューのをクリックして**BizTalk エクスプ ローラー**です。  
  
2.  BizTalk エクスプ ローラーで、 **BizTalk 管理データベース**の順に展開および**送信ポート**です。  
  
3.  右クリック**送信ポート**、クリックして**送信ポートの追加**です。  
  
4.  新しい送信ポートを作成 ウィンドウで、次のように選択します。**静的な一方向ポート**、順にクリック**OK**です。  
  
5.  静的な一方向送信ポートのプロパティ ウィンドウで、**名**ボックスで、送信ポートの名前を入力します。  
  
6.  左側のウィンドウでをクリックして**トランスポート**です。 右側のウィンドウでをクリックして**トランスポートの種類**を選択して**ファイル**トランスポートの種類。 横にある省略記号ボタン (...) をクリックして**アドレス (URI)**、ハード_ディスク上の場所を入力し、クリックして**OK**です。  
  
7.  左側のウィンドウでをクリックして**送信**をクリックして**送信パイプライン**、し、 **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**です。  
  
8.  左側のウィンドウでをクリックして**フィルターし、マップ**、クリックして**フィルター**です。  
  
9. 右側のペインの最初の行での**プロパティ** **Microsoft.Solutions.BTARN.GlobalSchemas.IsDuplicateMessage**ドロップダウン リストからのままにして、**演算子**として **==** 、入力**True**の**値**、し、**または**のドロップダウンリストから**グループ**です。  
  
10. 右側のペインで 2 番目の行の**プロパティ** **Microsoft.Solutions.BTARN.GlobalSchemas.IsOrphanMessage**ドロップダウン リストからのままにして、**演算子**として **==** 、し、入力**True**の**値**です。  
  
11. **[OK]**をクリックします。  
  
12. BizTalk エクスプ ローラーで、送信ポートの名前を右クリックし、をクリックして**Enlist**です。 送信ポートが参加して後、送信ポートを右クリックし、をクリックして**開始**です。  
  
## <a name="see-also"></a>参照  
 [プログラミング ガイド](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)