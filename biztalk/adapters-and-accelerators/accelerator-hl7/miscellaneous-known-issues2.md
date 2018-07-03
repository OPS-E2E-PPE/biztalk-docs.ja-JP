---
title: その他の既知の Issues2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- known issues
ms.assetid: 01cd896f-6c7f-4734-b953-81a92195a5c0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d0e845a6a178b66d2a817414666455eb20b5bb4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007859"
---
# <a name="miscellaneous-known-issues"></a>その他の既知の問題
このセクションには、その他のエラーに関する有用な情報が含まれています。  
  
## <a name="duplicate-errors-logged-for-the-same-message-segment-sequence-and-field-number"></a>同じメッセージ セグメント、シーケンス、およびフィールドの数のログでエラーが重複しています  
 複雑なデータのフィールドのコンポーネントでエラーがある場合の型、Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) このようなエラーはごとに 1 つのエラーが報告されます。 セグメント ID と、フィールドの数は同じになります。 HL7 のエラー レポート機構は、コンポーネントとサブコンポーネント レベルでのエラーの報告をサポートしていないために、エラー番号と説明が異なる場合があります。  
  
## <a name="segment-sequence-errors"></a>セグメントのシーケンス エラー  
 メッセージのセグメントが存在しないか、必要な場合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]エンジンで解析の最後の正しいセグメント内の「セグメントのシーケンス エラー (予期しない終了のメッセージの本文が見つかりません)」メッセージを報告します。  
  
## <a name="invalid-error-can-be-recorded-when-the-msh3-header-field-is-structurally-incorrect"></a>MSH3 ヘッダー フィールドが構造的に正しくない場合に、無効なエラーを記録できます。  
 MSH3 のヘッダー フィールドが構造的に正しくない場合、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]シリアライザーは、MSH5 ヘッダーに MSH3 フィールドの内容をコピーすることはできませんと[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]受信確認 (ACK) を送信することはできません。 MSH5 フィールドを MSH3 フィールドではない問題があったこと可能性があります。  
  
## <a name="access-database-errors"></a>データベースのアクセス エラー  
 HL7 の Access データベースには、次のエラーが含まれています。  
  
- HL7 V2.3 Access データベースに OBR セグメントのフィールドの 27 が、反復不能と必要なと正しくマークされたされません。 これで、変更が発生しました[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]スキーマのフィールドの反復可能なと省略可能な適切な値にします。  
  
- Field 2 とデータベースが正しくマークされた HL7 V2.3 access OBX セグメントの必須であり、OBX セグメント HL7 V2.3 Access データベース内のフィールド 10 が誤ってマークされていない繰り返し可能なようです。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]スキーマ、2 フィールドは省略可能としてマークされているおよび 10 フィールドは、繰り返し可能でマークされます。  
  
- データベースが正しくマークされた HL7 V2.3.1 access OBX セグメントの Field 4 が必要です。 このフィールドで、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]スキーマは省略可能として正しくマークされています。  
  
## <a name="logging-service-account-may-not-have-access-to-databases-that-are-not-created-by-the-setup-program"></a>サービス アカウントのログ記録がないは、セットアップ プログラムによって作成されないデータベースへのアクセス  
 セットアップ プログラムが作成した、新しく作成されたデータベースをポイントして、ログ ストアを構成するときに、新しいデータベースにアクセスするために表示されるログ記録サービス アカウントは指定できません。 ログ記録のサービス アカウントに新しく作成されたすべてのログ データベースにアクセスしてください。  
  
## <a name="leading-spaces-not-allowed-in-nm-and-si-data-types"></a>先頭のスペースは NM と SI のデータ型では使用できません。  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 先頭および末尾のスペースが含まれる NM と SI データ型のインスタンスを拒否します。  
  
## <a name="btahl7-accepts-a-value-of-0-for-hl7-v21-si-data-type"></a>BTAHL7 は、HL7 V2.1 SI データ型の「0」の値を受け入れます  
 HL7 V2.1 の HL7 標準で、「0」の値の対象は SI のデータ型のインスタンスでは許されません。 ただし、 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 「0」SI のデータ型のインスタンスで有効な値として受け入れます。  
  
## <a name="mismatch-of-source-and-destination-party-namespaces"></a>送信元と送信先のパーティの名前空間の不一致  
 名前空間が構成されている場合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラーで、**検証**HL7 V2 のタブがスキーマにソースの名前空間と一致しません。X のメッセージ、シリアライザーは、問題を明確に特定できないエラー メッセージを生成可能性があります。 セグメントのシーケンス エラーまたはメッセージ本文の予期しない終了が検出されたこのようなエラー メッセージがある可能性があります。 場合は、エラーの原因を説明することはできません、パーティの名前空間の不一致をチェックする可能性があります。  
  
## <a name="lack-of-segments-fts-or-bts-results-in-error-but-the-message-still-parses"></a>FTS または BTS 結果が、エラー、メッセージ、セグメントの欠如はまだ解析します。  
 ときに、 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] FHS または BHS、セグメントが含まれますが、対応するが含まれていませんが、バッチ メッセージを解析する逆アセンブラー FTS や BTS、セグメント化[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]エラーを生成、メッセージはまだ解析しますが、します。  
  
## <a name="modifying-a-message-header-tag-results-in-multiple-errors"></a>複数のエラーでメッセージ ヘッダー タグ結果を変更します。  
 オーケストレーション デザイナーでは、メッセージ ヘッダーのタグを変更する場合は「無効な最初のセグメント」または「セグメントのシーケンス エラー」など、わかりやすくないエラーが発生する可能性があります。  
  
## <a name="configuration-data-can-be-affected-by-other-biztalk-server-applications"></a>構成データは他の BizTalk Server アプリケーションによって影響を受けることができます。  
 カスタム データを入力した場合、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー、または構成データベースで、構成アプリケーション プログラミング インターフェイス (Api)、カスタム データをプログラムで使用してデータが格納されているセットの構成。  他の BizTalk アプリケーションから他のパーティに固有の情報の構成データベースを使用できます。 別のアプリケーションと同じ場所にデータを格納するかどうか、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成データを[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]データが正しく保存されない可能性があります。 このような場合、その他のアプリケーションのデータの格納場所を変更し、保存、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成データをもう一度です。  
  
## <a name="errors-might-not-be-logged-in-the-error-log-due-to-a-size-limitation-of-the-event-log-store"></a>エラーをイベント ログ ストアのサイズ制限が原因のエラー ログに記録しない可能性があります。  
 ときに、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]シリアライザーは多数のエラーを生成[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]イベント ログ ストアのサイズ制限が原因のエラーの一部がログオンしません。 状態と動作状況の追跡 (HAT) ツールでは、すべてのエラーを表示することができますが、エラー ログでそれらのすべてを表示することができません。  
  
## <a name="reinstalling-btahl7-under-a-different-folder-will-cause-the-default-receive-locations-not-to-work"></a>別のフォルダーの下、BTAHL7 を再インストールが原因、既定の受信場所に動作しないこと  
 別のフォルダーの下、BTAHL7 を再インストールすると、BatchControlPort または起動のチュートリアルで作成したポートにこれらのポートの Uri (ように、以前のインストールで呼ばれます) によって作成された新しいフォルダーと一致しないため、動作しないことの既定の場所セットアップ プログラム。 作業にこれらのポートでは、これらのポートの [FILE トランスポートのプロパティ] ダイアログ ボックスでフォルダー パスを更新する必要があります。  
  
 1 つ以上の MLLP ポートは、BTAHL7 をアンインストールすると、BizTalk に存在する場合、MLLP アダプターは削除されません。 発生すると、別の場所で製品をインストールする場合に、後にすべての新しいまたは古い MLLP ポートが機能しなくなります。 作業の MLLP、アンインストールして MLLP アダプターを再インストールする必要があります。 詳細についてを参照してください「MLLP アダプターはアンインストール中には削除されません」[その他の問題のトラブルシューティング](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-other-issues.md)します。  
  
## <a name="see-also"></a>参照  
 [既知の問題](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)