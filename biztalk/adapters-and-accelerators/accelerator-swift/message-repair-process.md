---
title: メッセージの修復処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- repairing messages
- errors, messages
- messages, errors
- validating, messages
- messages, validating
ms.assetid: 87b97cec-5796-4684-bcf0-53285aca7ee2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 442e49c347b4adf84dd7e6ee86c3b3595452cb34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22211194"
---
# <a name="message-repair-process"></a>メッセージの修復処理
既定では、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス データベースの保留キューに失敗したメッセージを中断します。 このプロセスは、成功したメッセージから個別に失敗したメッセージを処理します。 この既定のメカニズムを使用して、ただし、ある失敗したメッセージを取得し、それらを修復する機能が制限されます。 メッセージ修復 and New Submission 機能[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]により、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザー メッセージを修復して再送信します。 別[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザーは、修復を確認し、3 つ目は、修復を承認できます。  
  
> [!NOTE]
>  このコンテキストで、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザーは、部門別の修復ワークフロー内でロールを実行するユーザー。 この A4SWIFT ユーザーが定義されているし、プロファイル Web クライアントのユーザー リンク内の証明書に関連付けられています。 これは、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザーと同じではありません、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]で定義されているユーザー アカウント、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]でユーザーをグループ化、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]コンピューター管理ユーティリティです。 として機能している人、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザーがいる必要があります、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]ユーザー アカウントのメッセージを送信するときに、そのアカウントの証明書が使用できるようにします。 ただし、そのユーザーとしても使用できますの[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザー: 修理会社、検証、承認者、または作成者。 詳細については、次を参照してください。 [Message Repair and New Submission のロールの作成の部門と](../../adapters-and-accelerators/accelerator-swift/creating-departments-and-roles-for-message-repair-and-new-submission.md)です。  
  
 この修復ワークフローで[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]失敗したメッセージを一時停止しません。 失敗したメッセージの追加の処理を実行し、成功のメッセージの場合と同様に、メッセージ ボックスに、メッセージをドロップします。 修復オーケストレーションにメッセージをドロップする、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] MRSR サイト、ユーザーがのそれらの機能を実行できる[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム。  
  
## <a name="message-validation"></a>メッセージの検証  
 Message Repair and New Submission MRSR サイト修復のために、次の検証が失敗しているすべてのメッセージを送信します。  
  
-   フラット ファイル パーサー (未解析メッセージ) によって実行される構造の検証  
  
-   リーダーを検証する XML によって実行されるデータ検証  
  
-   ルールの検証ビジネス ルール エンジン (BRE) での実行に SWIFT ネットワークとの使用  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]SWIFT メッセージの転送されたエラーのコレクション オブジェクト内の検証中に発生したエラーを収集します。 修復プロセスには、XML と、エラーの一部としてメッセージに添付にシリアル化のエラー情報が含まれます。 またこの処理には、プロパティを昇格したメッセージの検証が失敗したことを示すメッセージをマークすることが含まれます ([!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed = = True)、およびエラーを報告するもう 1 つの昇格させたプロパティが検証ステージごとにカウントします。 次の結果として得られるマルチパート メッセージで構成されます。  
  
-   失敗したメッセージを含むボディ部  
  
-   エラー コレクション XML を含むエラー部分  
  
-   障害の状態を示すプロパティの昇格  
  
## <a name="message-repair"></a>Message Repair  
 MRSRDepartmentPolicy 内 MRSRDepartmentRule ビジネス ルールでは、部門は、失敗したメッセージを処理を決定します。 メッセージの修復オーケストレーションは、部門の修復のロールに関連付けられている受信トレイにメッセージをルーティングして修復ワークフローを開始します。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]修復ロールを実行するユーザーにメッセージを開く、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームで、メッセージを修復し署名および送信します。 オーケストレーションは、修復、キーの再検証、または承認のロールのそれぞれに修復されたメッセージをルーティングし、ワークフローが正常に完了したら、メッセージを送信ポートにルーティングします。  
  
 検証、に加えて[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]次を確認するメッセージの署名をチェックします。  
  
-   修復ワークフロー内のユーザーが同じ部門に属しています。  
  
-   各ユーザーが 1 回だけサインインします。  
  
-   一連のユーザーに対応する役割がその部門に定義されたワークフローの組み合わせに一致します。  
  
 部門の詳細については、次を参照してください。 [Message Repair and New Submission のロールの作成の部門と](../../adapters-and-accelerators/accelerator-swift/creating-departments-and-roles-for-message-repair-and-new-submission.md)です。  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]未解析のメッセージを修復することもできます。 ただし、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]修復未解析のメッセージのさまざまな処理を実行します。 詳細については、次を参照してください。[未解析のメッセージの修復](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md)です。