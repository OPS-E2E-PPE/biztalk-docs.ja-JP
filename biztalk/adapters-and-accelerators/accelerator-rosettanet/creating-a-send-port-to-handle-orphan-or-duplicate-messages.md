---
title: 孤立したメッセージまたは重複するメッセージを処理する送信ポートの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, duplicate messages
- messages, orphaned messages
- send ports, duplicate messages
- send ports, orphaned messages
- messages, send ports
ms.assetid: 61d51206-13e3-4d32-a184-866248db9b45
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4a6e166a891da2a3d393d176555c2b50deed044
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284843"
---
# <a name="creating-a-send-port-to-handle-orphan-or-duplicate-messages"></a>孤立したメッセージまたは重複するメッセージを処理する送信ポートを作成します。
このトピックでは、孤立したメッセージまたは重複するメッセージを削除するために使用できる送信ポートを設定する方法について説明します。  
  
 孤立したメッセージまたは重複メッセージは、場合に、問題になる可能性 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]パブリック プロセス オーケストレーションのメッセージの最初のコピー処理が完了した後、メッセージの追加のコピーを受信します。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] これらのメッセージを重複としてマークし、それらを中断します。 BizTalk 管理コンソールで、これらのメッセージを表示できます。 BizTalk 管理コンソールの詳細については、「を使用して、BizTalk 管理コンソール」で、BizTalk Server ヘルプを参照してください。  
  
 孤立したメッセージまたは重複メッセージは、確認するか、それらを削除するまでは、BizTalk 管理コンソールに残ります。 それらを削除する最も効果的な方法では、孤立したメッセージまたは重複するメッセージに設定されているフィルターと送信ポートを設定します。 BizTalk Server で使用可能な輸送手段を使用してそれらを移動することができます。 たとえば、ファイル トランスポートを使用して、移動できます。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] ハード ディスク上の場所にファイルとして、孤立したメッセージまたは重複するメッセージを送信します。 これにより、それらを簡単に削除します。 参加していると、停止状態で、中断状態としてのすべてのメッセージが送信された場合は表示その送信ポート、ポートを指定できます。  
  
> [!NOTE]
>  重複/孤立したメッセージを処理する送信ポートを作成する代わりに、これらのメッセージをメッセージ ボックス データベースから削除する特別なパイプライン コンポーネントを作成できます。 内の FixMsg コンポーネントを使用することができます、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] SDK テンプレートとして。 変更する必要がある、`IComponent.Execute`メソッドは null を返します。 これにより、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]コンポーネントを含むパイプラインに送信されたメッセージを破棄します。 このパイプライン コンポーネントをコンパイルし送信パイプラインに追加して、コンパイル、展開、およびシンク ポートの送信パイプラインを選択する必要があります。 詳細については、次を参照してください。"CustomComponent ([!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]サンプル)"で BizTalk Server のヘルプ。  
  
### <a name="to-create-a-send-port-to-handle-orphan-or-duplicate-messages"></a>孤立したメッセージまたは重複するメッセージを処理する送信ポートを作成するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の**ビュー** メニューのをクリックして**BizTalk エクスプ ローラー**です。  
  
2. BizTalk エクスプ ローラーで、 **BizTalk 管理データベース**、順に展開**送信ポート**します。  
  
3. 右クリックして**送信ポート**、 をクリックし、**送信ポートの追加**します。  
  
4. 新しい送信ポートを作成 ウィンドウで、次のように選択します。**静的な一方向ポート**、順にクリックします**OK**します。  
  
5. 静的な一方向送信ポートのプロパティ ウィンドウで、**名前**ボックスに、送信ポートの名前を入力します。  
  
6. 左側のウィンドウで次のようにクリックします。**トランスポート**します。 右側のウィンドウで次のようにクリックします。**トランスポートの種類**、選び**ファイル**トランスポートの種類。 横にある省略記号ボタン (…) をクリックします。**アドレス (URI)**、ハード_ディスク上の場所を入力し、クリック**OK**します。  
  
7. 左側のウィンドウで次のようにクリックします。**送信**、] をクリック**送信パイプライン**、し、[ **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**します。  
  
8. 左側のウィンドウで次のようにクリックします。**フィルターとマップ**、 をクリックし、**フィルター**します。  
  
9. 右側のウィンドウで 1 行目の**プロパティ**を選択します**Microsoft.Solutions.BTARN.GlobalSchemas.IsDuplicateMessage**ままにしてドロップダウン リストから、**演算子**として**==**、入力**True**の**値**、し、**または**のドロップダウンリストから**グループ**します。  
  
10. 右側のウィンドウで 2 行目の**プロパティ**を選択します**Microsoft.Solutions.BTARN.GlobalSchemas.IsOrphanMessage**ままにしてドロップダウン リストから、**演算子**として**==**、し、入力**True**の**値**します。  
  
11. **[OK]** をクリックします。  
  
12. BizTalk エクスプ ローラーで、送信ポートの名前を右クリックして**参加**します。 送信ポートが参加して、送信ポートを右クリックし、クリックして**開始**します。  
  
## <a name="see-also"></a>参照  
 [プログラミング ガイド](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)