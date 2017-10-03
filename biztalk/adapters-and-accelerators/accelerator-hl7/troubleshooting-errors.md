---
title: "エラーのトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- errors, troubleshooting
- troubleshooting, errors
ms.assetid: 08cc95a3-4be9-450f-a015-e031011158f7
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae7ad99b699da29d4d8680375f88e4d4a74ff66a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-errors"></a>エラーのトラブルシューティング
このセクションの内容に関連する問題に対処[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]でエラーが発生します。  
  
## <a name="the-mllp-adapter-can-run-only-on-a-single-host-instance"></a>MLLP アダプターを 1 つのホスト インスタンスでのみ実行できます。  
  
### <a name="symptom"></a>現象  
 トランスポートの種類が MLLP の受信場所と別の既存の受信場所よりも別の受信ハンドラーを有効にすることはできません。 さらに、参加させるし、別の既存の送信ポートよりも別の送信ハンドラーに送信ポートを開始できません。  
  
**考えられる原因**: 使用できるは 1 つの MLLP のみハンドラーを単一のサーバー上の受信 (または送信) します。 さらに、URI が指定されている受信場所 (または送信ポート) の (MLLP トランスポートのプロパティ内のホスト名) は、"localhost"をする必要がありますか、または受信 (または送信) のアダプター ハンドラーのホストのインスタンスでサーバー名が実行されています。  
  
**解像度**: 単一のサーバーにすべて MLLP の受信場所 (または送信ポート) の同じ受信 (または送信) のハンドラーを指定します。  
  
## <a name="msh-and-ack-schemas-must-be-added-to-only-one-project"></a>MSH と確認のスキーマは、1 つしかプロジェクトに追加する必要があります。  
  
### <a name="symptom"></a>現象  
 プロジェクトをビルドしようとすると、次のエラーのいずれかを取得します。  
  
`Error: Cannot locate document specification as multiple schemas match the message type "http://microsoft.com/HealthCare/HL7/2X#MSH_24_GLO_DEF"`
  
`Schema http://microsoft.com/HealthCare/HL7/2X#MSH_24_GLO_DEF not found`
  
**考えられる原因**:「MSH と確認のスキーマ (MSH_25_GLO_DEF.xsd と ACK_24_GLO_DEF.xsd) は、複数のプロジェクトで配置されています。  
  
**解像度**: MSH_25_GLO_DEF.xsd と ACK_24_GLO_DEF.xsd が 1 つしかプロジェクトに追加されたことを確認してください。  
  
## <a name="exception-of-type-systemoutofmemoryexception-has-thrown-an-error-in-the-event-log"></a>System.OutOfMemoryException の種類の例外が、イベント ログにエラーをスローします。  
  
### <a name="symptom"></a>現象  
 イベント ログに、次のようなエラーを取得します。  
  
`Exception of type System.OutOfMemoryException has thrown an error.`
  
**考えられる原因**: 一部のメッセージの数が多いの処理中に[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]エンジン コンポーネント メモリ リークが発生する可能性があります。  
  
**解像度**: 再起動[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。  
  
## <a name="header-serialization-generates-an-error-in-the-event-viewer"></a>ヘッダーのシリアル化では、イベント ビューアーにエラーが生成されます。  
  
### <a name="symptom"></a>現象  
 状態と動作状況の追跡 (HAT) ツールでメッセージが成功を示す場合でもは、イベント ログ内の次のようなエラーを取得します。  
  
`An error happened in the header during serialization.`
  
**考えられる原因**: メッセージ ヘッダーの変換の値が正しく設定されていない[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。  
  
**解像度**: の値が確認 MSH マップ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。  
  
## <a name="duplicate-event-id-4133-serializer-errors-are-logged"></a>イベント ID 4133 シリアライザーの重複エラーが記録されます。  
  
### <a name="symptom"></a>現象  
 イベント ID 4133:「エラーが発生したヘッダーのシリアル化中に」は、無効な MSH11 値を持つメッセージのすべてのインスタンスに対して 2 回発生します。  
  
**考えられる原因**: イベント ログに重複するエラーが発生しない (コミットおよびアプリケーション Ack) の 2 つの受信確認の処理中にエラーが発生しました。 代わりに、2 つの Ack の各イベント ID 4133 の 1 つが表示されます。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]各 ACK 生成用のログ エントリを作成します。  
  
**解像度**: メッセージが正しく書式設定とデータが設定された MSH11 フィールドを持つことを確認してください。  
  
## <a name="send-pipeline-generates-an-error-when-using-the-2-way-mllp-adapter"></a>送信パイプラインで両方向 MLLP アダプターを使用するときにエラーが生成されます。  
  
### <a name="symptom"></a>現象  
 イベント ログに、次のようなエラーを取得します。  
  
`There was a failure executing the send pipeline: "[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2XPipelines.[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2XSendPipeline" Source: "[!INCLUDE[btsCoName](../../includes/btsconame-md.md)].Solutions.[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].HL72fAsm" Send Port: "<*host name: port number*>" Reason: Message does not contain a part with name MSHSegment.`
  
**考えられる原因**: 受信確認の受信側のアプリケーションが応答しないと[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]受信側のアプリケーションからの応答を指定してください。  
  
**解像度**: 仕様では、これは、エラー メッセージを無視することができます。  
  
## <a name="see-also"></a>参照  
 [HL7 のトラブルシューティングと既知の問題](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-and-known-issues-in-hl7.md)