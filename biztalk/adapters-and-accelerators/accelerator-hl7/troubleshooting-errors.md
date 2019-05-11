---
title: エラーのトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- errors, troubleshooting
- troubleshooting, errors
ms.assetid: 08cc95a3-4be9-450f-a015-e031011158f7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4d8aaba0556d0f5e1f14b50bdabe7392d068103
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65286586"
---
# <a name="troubleshooting-errors"></a>エラーのトラブルシューティング
このセクションでは、関連する問題を取り上げます[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]エラーが発生しました。  
  
## <a name="the-mllp-adapter-can-run-only-on-a-single-host-instance"></a>MLLP アダプターを 1 つのホスト インスタンスでのみ実行できます。  
  
### <a name="symptom"></a>現象  
 トランスポートの種類が MLLP の受信場所と別の既存の受信場所よりも、別の受信ハンドラーを有効にすることはできません。 さらに、参加させるし、既存の別の送信ポートよりも別の送信ハンドラーと送信ポートの開始できません。  
  
**考えられる原因**:1 つの MLLP を使用することができますのみハンドラーは単一のサーバー上の受信 (または送信) します。 さらに、URI が指定されている受信場所 (または送信ポート) (MLLP トランスポートのプロパティ内のホスト名) は、"localhost"をする必要がありますか、または受信 (または送信) のアダプター ハンドラーのホストのインスタンスでサーバー名が実行されています。  
  
**解像度**:すべて MLLP の受信場所 (または送信ポート) の単一のサーバーで同じ受信 (または送信) ハンドラーを指定します。  
  
## <a name="msh-and-ack-schemas-must-be-added-to-only-one-project"></a>MSH と確認のスキーマは、1 つしかプロジェクトに追加する必要があります。  
  
### <a name="symptom"></a>現象  
 プロジェクトをビルドしようとしたときに、次のエラーのいずれかを取得します。  
  
`Error: Cannot locate document specification as multiple schemas match the message type "http://microsoft.com/HealthCare/HL7/2X#MSH_24_GLO_DEF"`
  
`Schema http://microsoft.com/HealthCare/HL7/2X#MSH_24_GLO_DEF not found`
  
**考えられる原因**:MSH と確認のスキーマ (MSH_25_GLO_DEF.xsd と ACK_24_GLO_DEF.xsd) は、複数のプロジェクトで配置されています。  
  
**解像度**:MSH_25_GLO_DEF.xsd と ACK_24_GLO_DEF.xsd が 1 つしかプロジェクトに追加されたことを確認します。  
  
## <a name="exception-of-type-systemoutofmemoryexception-has-thrown-an-error-in-the-event-log"></a>型 System.OutOfMemoryException 例外がイベント ログにエラーをスローします。  
  
### <a name="symptom"></a>現象  
 イベント ログに以下のようなエラーが発生しました。  
  
`Exception of type System.OutOfMemoryException has thrown an error.`
  
**考えられる原因**:いくつかのメッセージの数が多いの処理中に[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]エンジン コンポーネント メモリ リークが発生する可能性があります。  
  
**解像度**:[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を再起動します。  
  
## <a name="header-serialization-generates-an-error-in-the-event-viewer"></a>ヘッダーのシリアル化では、イベント ビューアーでエラーが生成されます。  
  
### <a name="symptom"></a>現象  
 イベント ログに以下のようなエラーが発生した場合でも、状態と動作状況の追跡 (HAT) ツールでメッセージが成功を示します。  
  
`An error happened in the header during serialization.`
  
**考えられる原因**:メッセージ ヘッダーの変換値が正しく設定されていない[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。  
  
**解像度**:MSH マップの値を検証[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。  
  
## <a name="duplicate-event-id-4133-serializer-errors-are-logged"></a>イベント ID 4133 シリアライザーの重複エラーがログに記録されます。  
  
### <a name="symptom"></a>現象  
 イベント ID 4133 –「エラーが発生したヘッダーのシリアル化中に」は有効でない MSH11 値を持つメッセージのすべてのインスタンスに対して 2 回に発生します。  
  
**考えられる原因**:イベント ログに重複するエラーのない (コミットおよびアプリケーションの Ack) の 2 つの受信確認の処理中にエラーが発生しました。 代わりに、2 つの Ack の各イベント ID 4133 の 1 つが表示されます。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] それぞれの ACK 生成のログ エントリを作成します。  
  
**解像度**:正しく書式設定された、指定済み MSH11 フィールドをメッセージがあることを確認します。  
  
## <a name="send-pipeline-generates-an-error-when-using-the-2-way-mllp-adapter"></a>送信パイプラインでは、双方向の MLLP アダプターを使用する場合、エラーが生成されます。  
  
### <a name="symptom"></a>現象  
 イベント ログに以下のようなエラーが発生しました。  
  
`There was a failure executing the send pipeline: "[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2XPipelines.[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2XSendPipeline" Source: "Microsoft.Solutions.[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].HL72fAsm" Send Port: "<*host name: port number*>" Reason: Message does not contain a part with name MSHSegment.`
  
**考えられる原因**:受信確認では、受信側アプリケーションが応答しないと[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]受信側アプリケーションからの応答を指定してください。  
  
**解像度**:仕様では、これは、エラー メッセージは無視できます。  
  
## <a name="see-also"></a>参照  
 [HL7 のトラブルシューティングと既知の問題](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-and-known-issues-in-hl7.md)