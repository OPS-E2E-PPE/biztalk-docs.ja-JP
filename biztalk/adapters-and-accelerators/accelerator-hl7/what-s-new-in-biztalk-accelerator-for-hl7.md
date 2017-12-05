---
title: "BizTalk Accelerator 用 HL7 の新機能 |Microsoft ドキュメント"
description: "変更し、さまざまなバージョンの BizTalk Server HL7 アクセラレータの更新"
ms.custom: 
ms.date: 11/22/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e98595a1-2d1e-488e-8a97-7cd561948b3b
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3cdb992f749633bd517d6cad7f1acce926157c1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="whats-new-in-biztalk-accelerator-for-hl7"></a>BizTalk Accelerator 用 HL7 の新機能
変更し、更新で、[!INCLUDE[HL7_CurrentVersion_FirstRef_md](../../includes/hl7-currentversion-firstref-md.md)]です。 

## <a name="biztalk-server-2016"></a>BizTalk Server 2016

|機能|Description|  
|---|---| 
| **LOB への接続を開始します。** | MLLP アダプターを使用して[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]開始またはリモートの基幹業務 (LOB) のサーバー システムへの接続を開始できます。 LOB 接続を待機しにメッセージを送信[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]MLLP アダプターを使用します。 MLLP いくつかの新しいプロパティを受信場所をこのオプションを構成します。 次のチュートリアルを参照してください。 <br/><ul><li>[手順 4. で、エンド ツー エンドのチュートリアル](../../adapters-and-accelerators/accelerator-hl7/step-4-create-receive-port-to-accept-adt^a03-messages-from-adt-using-mllp.md)</li><li>[手順 4. で interrogative チュートリアル](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-receive-port-for-accepting-adt-query-messages.md)</li><li>[Interrogative チュートリアルの手順 5](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-receive-port-for-accepting-his-messages.md)</li><li>[バッチ処理のチュートリアルの手順 4](../../adapters-and-accelerators/accelerator-hl7/step-4-create-a-receive-port-for-accepting-the-batch-message.md)</li></ul>[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]し、以前のバージョン、HL7 MLLP の受信アダプター MLLP アダプターを接続するリモートの LOB サーバーまで待機し、LOB メッセージを送信します。 <br/><br/>参照してください[BTAHL7 によるメッセージのルーティング](../../adapters-and-accelerators/accelerator-hl7/how-btahl7-routes-messages.md)詳細についてはします。|

## <a name="biztalk-server-2013-r2"></a>BizTalk Server 2013 R2  
  
|機能|Description|  
|-------------|-----------------|  
|**64 ビット サポート**|MLLP アダプターと HL7 パイプラインは、32 ビットおよび 64 ビット ホスト インスタンスで実行できます。<br /><br /> [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]インストールには、32 ビット インストール パッケージと 64 ビット インストール パッケージが含まれています。 32 ビット コンピューターでは、32 ビット パッケージのみをインストールします。 64 ビット コンピューターで 32 ビットのインストール**または**64 ビット パッケージです。 <br/><br/>**重要:** 64 ビット サポートを使用してのみ、64 ビット パッケージをインストールします。 64 ビット パッケージでは、アダプターとパイプラインの実行を 32 ビット モードと 64 ビット モードの両方で有効にできます。|  
|**v2.6 スキーマのサポート**|サポートは次のとおりです。<br /><br /> -   **BTAHL7V26Common**プロジェクト: v2.6 スキーマが含まれています。<br />-   **BTAHL7Common**プロジェクト: v2.6 スキーマと; v2.6 メッセージに対する受信確認の生成、ACK_26_GLO_DEF 受信確認スキーマが含まれています。<br />-   **MSH_25_GLO_DEF**スキーマ: 新しいメッセージ v2.6 スキーマに含まれているし、引き続きすべて v2 をサポートするヘッダー フィールドのハンドル*。x*スキーマです。|  
|**動的 MLLP アダプターのサポート**|プロパティを使用してランタイムを一方向または双方向 (要求-応答) で構成できますアダプターは送信ポートです。 参照してください[動的 MLLP アダプター](../../adapters-and-accelerators/accelerator-hl7/dynamic-mllp-adapter.md)です。|  
|**「フリー テキスト」のサポート**|フィールドやセグメントが"FreeText"として定義されるフィールド/セグメント内の文字データは解析されません。 参照してください[フリー テキストを使用してエンコード文字](../../adapters-and-accelerators/accelerator-hl7/encoding-characters-using-free-text.md)です。|  
|**ACK または NACK 無効な MSH のメッセージが送信されます。**|使用して、 **ReturnErrorForInvalidMSH3**レジストリ キー、否定確認応答 (NACK) は、パーティに送信次が発生した場合。<br /><br /> -無効な MSH3 (HL7 構成エクスプ ローラーでは、パーティが定義されていません) <br />    **AND**<br />-MSH15 と MSH16 メッセージの値が null または空<br /><br /> NACK を送信するには、次のレジストリ キーを 1 に設定してホスト インスタンスを再起動しています。<br /><br /> 32 ビット ホスト:`HKLM\SOFTWARE\Microsoft\BizTalk Accelerator for HL7`<br /><br /> 64 ビット ホスト:`HKLM\ SOFTWARE\Wow6432Node\Microsoft\BizTalk Accelerator for HL7` <br/><br/>**ヒント:**ポートが、失敗したメッセージをサブスクライブできます。 <ul><li>使用して、 **BTAHL7Schemas.ParseError = True**条件をフィルター処理します。</li><li>使用して、 **Pass Through**パイプライン。</li></ul>|  
|**ACK メッセージ インスタンスはアクティブのまま**|アップ ストリームのシステムへの接続エラーがある場合、アクティブな状態のままでアップ ストリームのシステムに送信された受信確認 (ACK)。<br /><br /> 新しい動作: アップ ストリームのシステムへの接続エラーがある場合は、ACK メッセージが中断されます。|  
|**送信しない\<SB\>**|このプロパティは、受信アダプターのポート設定のプロパティに追加されます。 このプロパティを有効にするには設定、 **UseMLLPTransACK**値。<br /><br /> 、設定すると**False** (既定)、メッセージの送信にデータが始まる場合\<SB\>です。 たとえば、次のメッセージが送信されます。<br /> `<SB\>DataData<CR\>DataData<CR\>…`<br/><br />、設定すると**True**、データが不足している場合、アダプターがメッセージを送信\<SB\>最初にします。 たとえば、次のメッセージが送信されます。<br /> `DataData<CR\>DataData<CR\>…` <br/><br/>**重要:**双方向送信ポートの場合は**を送信しない\<SB\>** を送信しません SB メッセージで、ダウン ストリーム システムにし、True に設定します。 同時にダウン ストリーム システムから SB が不足している ACK を受信できます。|  
|**見つからないを受け入れる\<SB\>**|このプロパティは、送信アダプターのポート設定のプロパティに追加されます。 このプロパティを有効にするには設定、 **UseMLLPTransACK**値。<br /><br /> 、設定すると**False** (既定)、アダプターはエラーを返します、データが不足している場合は\<SB\>最初にします。 たとえば、次のメッセージには、エラーが返されます。<br /> `DataData<CR\>DataData<CR\>…`<br/><br />、設定すると**True**、データが不足している場合、アダプターは、メッセージを受信できる\<SB\>最初にします。 たとえば、次のメッセージが受信します。<br /> `<SB\>DataData<CR\>DataData<CR\>…` <br />`DataData<CR\>DataData<CR\>…` <br/><br/>**重要:**場合は、双方向受信ポートが**見つからない受け入れる\<SB\>** アップ ストリームのシステムからのメッセージに不足している SB を使用し、True に設定します。 同時には送信しません SB をアップ ストリームのシステム。|  
  
## <a name="biztalk-server-2013"></a>BizTalk Server 2013  
  
 次の機能強化は、以前のリリースに含まれていた。  
  
-   回復可能なインターチェンジ HL7 パイプラインのサポート バッチのバッチをシナリオです。  
  
 次の機能は、以前のリリースで削除されました。  
  
-   正常性の動作状況の追跡機能は BizTalk Server から削除ため BTAHL7 から監査機能が削除しますが、ログ記録はそのまま残ります。  
  
 次の機能は、以前のリリースで変更されました。  
  
-   「監査とログ記録サービス」は「HL7 ログ サービス」として名前を変更します。  

## <a name="see-also"></a>参照

[BizTalk Server 2016 の新機能](../../install-and-config-guides/what-s-new-in-biztalk-server-2016.md)  
[BizTalk Server 2013 R2 と 2013 の新機能](../../install-and-config-guides/what-s-new-in-biztalk-server-2013-and-2013-r2.md)