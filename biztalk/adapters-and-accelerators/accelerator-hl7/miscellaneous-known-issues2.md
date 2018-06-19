---
title: その他の既知 Issues2 |Microsoft ドキュメント
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
ms.openlocfilehash: af644ead6ecb825d6d6960145958c176946e844c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207066"
---
# <a name="miscellaneous-known-issues"></a>その他の既知の問題
このセクションには、その他のエラーに関する有益な情報が含まれています。  
  
## <a name="duplicate-errors-logged-for-the-same-message-segment-sequence-and-field-number"></a>同じメッセージ セグメント、シーケンス、およびフィールドの番号はログに記録の重複エラー  
 複合データ型のフィールドのコンポーネントでエラーがある場合[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) はこのようなエラーはごとに 1 つのエラーを報告します。 セグメント ID とフィールドの数は同じです。 HL7 エラー レポート機構は、コンポーネントとサブコンポーネント レベルでのエラーの報告をサポートしていないために、エラー番号と説明が異なる場合があります。  
  
## <a name="segment-sequence-errors"></a>セグメントのシーケンス エラー  
 メッセージのセグメントが存在しない場合、必要な場合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]エンジンで解析の最後の正しいセグメント内の「シーケンス エラー (メッセージ本文が見つかりましたの予期しない終了) をセグメント化」メッセージを報告します。  
  
## <a name="invalid-error-can-be-recorded-when-the-msh3-header-field-is-structurally-incorrect"></a>MSH3 ヘッダー フィールドが構造的に正しくない場合に、無効なエラーを記録することができます。  
 MSH3 ヘッダー フィールドが構造的に正しくない場合、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]シリアライザーは MSH5 ヘッダーに MSH3 フィールドの内容をコピーすることはできませんと[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]確認 (ACK) を送信することはできません。 問題が MSH5 フィールドを MSH3 フィールドではありませんが、この可能性があります。  
  
## <a name="access-database-errors"></a>データベースのアクセス エラー  
 HL7 Access データベースには、次のエラーが含まれています。  
  
-   OBR セグメント HL7 V2.3 Access データベース内のフィールド 27 が誤って、反復不可能と必須としてマークします。 これで、変更が発生した[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]repeatable とオプションの適切な値にスキーマのフィールドです。  
  
-   データベースが誤ってマークとして HL7 V2.3 access OBX セグメントのフィールドの 2 は、次の必須であり、OBX セグメント HL7 V2.3 Access データベース内のフィールド 10 が誤ってマーク反復可能なようです。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]スキーマの場合、2 フィールドは省略可能としてマークされているし、フィールド 10 は繰り返し可能とマークします。  
  
-   データベースが誤ってマークとして HL7 V2.3.1 access OBX セグメントのフィールド 4 が必要です。 このフィールドで、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]スキーマは正しく省略可能としてマークされています。  
  
## <a name="logging-service-account-may-not-have-access-to-databases-that-are-not-created-by-the-setup-program"></a>サービス アカウントのログ記録がないはセットアップ プログラムによって作成されないデータベースへのアクセス  
 新しく作成されたデータベースのセットアップ プログラムを作成できませんでしたをポイントするログ ストアを構成するときに、新しいデータベースがアクセスするために表示されるログ記録サービス アカウントをない可能性があります。 ログ記録のサービス アカウントが新しく作成されたすべてのログ データベースへのアクセスを持っていることを確認します。  
  
## <a name="leading-spaces-not-allowed-in-nm-and-si-data-types"></a>先頭のスペース NM と SI のデータ型では使用できません。  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]先頭および末尾のスペースが含まれる NM および SI データ型のインスタンスを拒否します。  
  
## <a name="btahl7-accepts-a-value-of-0-for-hl7-v21-si-data-type"></a>BTAHL7 は、HL7 V2.1 SI データ型の「0」の値を受け入れます  
 HL7 の標準 HL7 バージョン 2.1 以降での「0」の値は SI データ型のインスタンスで使用できません。 ただし、 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] SI データ型のインスタンスで有効な値として「0」を受け入れます。  
  
## <a name="mismatch-of-source-and-destination-party-namespaces"></a>送信元と送信先のパーティの名前空間の不一致  
 名前空間が構成されている場合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラーで、**検証** タブを HL7 V2 用として、スキーマ内のソースの名前空間は一致しません。X のメッセージ、シリアライザーが問題を明確に特定できないエラー メッセージを生成する可能性があります。 このようなエラー メッセージ セグメント シーケンス エラーまたは予期しないメッセージの本文の終わりが検出された可能性があります。 エラーの原因を説明することはできない場合、は、パーティの名前空間が一致をチェックする可能性があります。  
  
## <a name="lack-of-segments-fts-or-bts-results-in-error-but-the-message-still-parses"></a>FTS または BTS されますが、エラー、メッセージのセグメントが不足しているがまだ解析します。  
 ときに、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]逆アセンブラーが FHS または BHS、セグメントが含まれていますが、対応するが含まれていないバッチ メッセージを解析 FTS や BTS、セグメント化[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]はエラーを生成、メッセージはまだ解析がします。  
  
## <a name="modifying-a-message-header-tag-results-in-multiple-errors"></a>複数のエラーでメッセージのヘッダー タグ結果を変更します。  
 オーケストレーション デザイナーでは、メッセージ ヘッダー タグを変更する場合は「無効な最初のセグメント」または"セグメント シーケンス error"など、わかりやすくエラーが発生する可能性があります。  
  
## <a name="configuration-data-can-be-affected-by-other-biztalk-server-applications"></a>構成データを他の BizTalk Server アプリケーションによって受けることができます。  
 カスタム データを入力した場合、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー、または構成アプリケーション プログラミング インターフェイス (Api) でカスタム データをプログラムで使用してデータが、構成データベースに格納されているセットの構成。  構成データベースは、他の BizTalk アプリケーションからその他のパーティに固有の情報を使用することができます。 別のアプリケーションと同じ場所にデータを格納するかどうか、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成データ、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]データが正しく保存されない可能性があります。 この場合、その他のアプリケーションのデータの格納場所を変更し、保存、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成データをもう一度です。  
  
## <a name="errors-might-not-be-logged-in-the-error-log-due-to-a-size-limitation-of-the-event-log-store"></a>エラーをイベント ログ ストアのサイズの制限により、エラー ログに記録されません可能性があります。  
 ときに、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]シリアライザーは多数のエラーを生成[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]一部のイベント ログ ストアのサイズの制限により、エラーがログオンしない場合があります。 状態と動作状況の追跡 (HAT) ツールで、すべてのエラーを表示することができますが、エラー ログでそれらのすべてを表示することができません。  
  
## <a name="reinstalling-btahl7-under-a-different-folder-will-cause-the-default-receive-locations-not-to-work"></a>別のフォルダーの下にある BTAHL7 を再インストールが原因と、既定の受信場所が機能しません。  
 別のフォルダーの下にある BTAHL7 を再インストールすると、BatchControlPort Launch Tutorial によって作成されたポートするかどうかへの Uri を (以前のインストールで呼ばれます)、これらのポートが作成した新しいフォルダーと一致しないために、機能の既定の場所セットアップ プログラム。 作業をこれらのポートでは、これらのポートの FILE トランスポートのプロパティ ダイアログ ボックスでフォルダー パスを更新する必要があります。  
  
 1 つまたは複数の MLLP ポートは、BTAHL7 のアンインストール時に、BizTalk に存在する場合、MLLP アダプターは削除されません。 発生した後、別の場所で製品をインストールする場合、すべての新しいまたは古い MLLP ポートは機能しなくなります。 作業に MLLP、アンインストールして MLLP アダプターを再インストールする必要があります。 詳細についてを参照してください「MLLP アダプターがアンインストール時に削除されない」[その他の問題のトラブルシューティング](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-other-issues.md)です。  
  
## <a name="see-also"></a>参照  
 [既知の問題](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)