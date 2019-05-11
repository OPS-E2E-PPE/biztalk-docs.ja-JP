---
title: メッセージの修復処理 |Microsoft Docs
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
ms.openlocfilehash: 6f9f42b23a7849c918f583946fd2c8e7cace4bf8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377209"
---
# <a name="message-repair-process"></a>メッセージの修復処理
既定では、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス データベースの保留キューに失敗したメッセージを中断します。 このプロセスは、成功したメッセージから個別に失敗したメッセージを処理します。 この既定のメカニズムを使用して、ただし、ある失敗したメッセージを取得し、それらを修復する機能が制限されます。 メッセージの修復 and New Submission 機能[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]により、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザー メッセージを修復して再送信します。 もう 1 つ[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]修復をユーザーが確認し、3 つ目は、修復を承認できます。  
  
> [!NOTE]
>  このコンテキストで、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザーは、部門別の修復のワークフローでロールを実行するユーザー。 この A4SWIFT ユーザーが定義されているし、プロファイルの Web クライアントの [ユーザー] リンク内の証明書に関連付けられています。 これは、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザーが同じではありません、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]で定義されているユーザー アカウント、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]でユーザーをグループ化、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]コンピューター管理ユーティリティです。 として機能している人、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザーがいる必要があります、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]アカウントのユーザーは、メッセージを送信するときにそのアカウントの証明書を使用できるようにします。 ただし、そのユーザーとしても利用できるその他の[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザー: 修理会社、検証、承認者、または作成者です。 詳細については、次を参照してください。[作成部門および Message Repair and New Submission のロール](../../adapters-and-accelerators/accelerator-swift/creating-departments-and-roles-for-message-repair-and-new-submission.md)します。  
  
 この修復ワークフローで[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]失敗したメッセージを一時停止しません。 失敗したメッセージの追加の処理を実行し、成功したメッセージと同様に、メッセージ ボックスにはメッセージを削除します。 修復オーケストレーションにメッセージを削除する、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] MRSR サイト、ユーザーが自分の機能を実行できます[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム。  
  
## <a name="message-validation"></a>メッセージの検証  
 Message Repair and New Submission MRSR サイト修復のために、次の検証が失敗しているすべてのメッセージを送信します。  
  
- フラット ファイル パーサー (未解析メッセージ) によって実行される構造の検証  
  
- リーダーを検証する XML によって実行されるデータの検証  
  
- ルールのビジネス ルール エンジン (BRE) で実行される検証を行う SWIFT ネットワークと使用状況  
  
  [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] SWIFT メッセージで転送されるエラーのコレクション オブジェクトの検証中に発生したエラーを収集します。 修復処理には、エラーの一部としてメッセージに添付し、XML にシリアル化のエラー情報が含まれます。 またこの処理には、メッセージの検証が失敗したことを示す昇格させたプロパティを持つメッセージをマークすることが含まれます ([!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed True = =) と、エラーを報告するもう 1 つの昇格させたプロパティが各検証ステージの数します。 結果のマルチパート メッセージは、以下の構成します。  
  
- 失敗したメッセージを含むボディ部  
  
- エラーの部分がエラー コレクションの XML を含む  
  
- エラー状態を示すプロパティの昇格  
  
## <a name="message-repair"></a>メッセージの修復  
 MRSRDepartmentPolicy 内 MRSRDepartmentRule ビジネス ルールは、どの部門が、失敗したメッセージを処理するかを判断します。 メッセージの修復オーケストレーションは、部門の修復のロールに関連付けられた受信トレイにメッセージをルーティングして修復ワークフローを開始します。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]修復ロールを実行するユーザーにメッセージを開くと、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームで、メッセージの修復し署名され、送信されます。 オーケストレーションでは、それぞれの修復、キー更新の確認、または承認の役割に修復されたメッセージをルーティングし、ワークフローが正常に完了した後は、送信ポートにメッセージをルーティングします。  
  
 検証、に加えて[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]次を確認するメッセージの署名をチェックします。  
  
- 修復ワークフロー内のユーザーが同じ部門に属しています。  
  
- 各ユーザーが 1 回だけ署名します。  
  
- ユーザーに対応するロールのシーケンスがその部門に対して定義されているワークフローのシーケンスと一致します。  
  
  部門の詳細については、次を参照してください。[作成部門および Message Repair and New Submission のロール](../../adapters-and-accelerators/accelerator-swift/creating-departments-and-roles-for-message-repair-and-new-submission.md)します。  
  
  [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 未解析メッセージを修復することもできます。 ただし、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]修復未解析メッセージのさまざまな処理を実行します。 詳細については、次を参照してください。[未解析メッセージの修復](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md)します。