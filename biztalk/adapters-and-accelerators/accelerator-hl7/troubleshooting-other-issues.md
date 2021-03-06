---
title: その他の問題のトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting
ms.assetid: 1f115f64-45ce-445d-ab18-092f4a6a232c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bab6578c6a9fcbc4a9b1349833604188d1d7884c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65286426"
---
# <a name="troubleshooting-other-issues"></a>その他の問題のトラブルシューティング
Microsoft に関連するその他の問題に対処[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]します。  
  
## <a name="message-rejected-by-the-btahl7-engine"></a>メッセージは、BTAHL7 エンジンによって拒否されました  
  
### <a name="symptom"></a>現象  
 メッセージは、メッセージ エンジンによってランダムに拒否されます。  
  
**考えられる原因**:HL7 標準に従ってテーブル 0338 の列挙値には、"L & は"の値が含まれています。 PRA セグメントのフィールド 6 では、この値を含めることができます。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] "&"の文字を扱う、区切り記号として、メッセージは拒否されます。  
  
**解像度**:これには、この問題の 3 つの考えられる解決策があります。  
  
1.  メッセージのインスタンスでは、L\T\I 文字の組み合わせを使用するなど、エスケープ シーケンスを"&"の文字を処理します。  
  
2.  スキーマで PRA 6 で"LI"の列挙値を追加し、メッセージ インスタンスでこの値を代わりに使用します。  
  
3.  MSH2; でまったく異なるサブコンポーネントの区切り記号を使用します。ただし、この特定のソリューションは、環境に応じて現実的でない可能性があります。  
  
## <a name="cannot-edit-the-hl7-schema-using-visual-studio"></a>Visual Studio を使用して、HL7 スキーマを編集することはできません。  
  
### <a name="symptom"></a>現象  
 Microsoft を使用して、HL7 スキーマを編集することはできません[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。  
  
**考えられる原因**:[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]一部 HL7 スキーマはサポートしません。  
  
**解像度**:HL7 スキーマを編集するのにには、Microsoft メモ帳などの他のエディターを使用します。  
  
## <a name="message-handling-fails-with-no-errors-logged"></a>ログイン エラーのないメッセージの処理が失敗します。  
  
### <a name="symptom"></a>現象  
 システムは、エラー メッセージを記録または中断されたメッセージ キューにメッセージを配置することがなく、メッセージを処理します。  
  
**考えられる原因**:**HeaderSpecType**と**DocumentSpecType**プロパティの値は大文字小文字を区別します。 パイプラインを展開するときにこれらの名前で入力ミスにメッセージをログに記録するエラーなしで削除し、べき可能性があります。  
  
**解像度**:使用する場合は、大文字小文字の区別を観察、 **HeaderSpecType**と**DocumentSpecType**プロパティ値の名前。  
  
## <a name="message-header-fields-are-not-validated-correctly"></a>メッセージ ヘッダー フィールドが正しく検証されていません  
  
### <a name="symptom"></a>現象  
 ヘッダー フィールドの検証に失敗しました。  
  
 理由: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]シリアライザーは、実際のヘッダー フィールドのコンテキスト プロパティではなく、昇格されたプロパティを検証します。  
  
**考えられる原因**:ヘッダーから、オーケストレーションやマップに対応する昇格させたプロパティに、変更が発生しました。  
  
**解像度**:MSH1、MSH2、および MSH5 メッセージ ヘッダーのコンテキスト プロパティ{1-3}のデータと同期されているように更新する必要があります。  
  
## <a name="the-mllp-adapter-is-not-removed-during-uninstall"></a>MLLP アダプターがアンインストール中に削除されません。  
  
### <a name="symptom"></a>現象  
 BTAHL7 セットアップ プログラムは、BTAHL7 のアンインストール時に MLLP アダプターを削除できませんでした。  
  
**考えられる原因**:トランスポートの種類が MLLP の受信場所または送信ポートが発生しました。 いずれかの BizTalk Server プロジェクトで参照されている場合、BTAHL7 セットアップは MLLP アダプターを削除できません。  
  
**解像度**:BTAHL7 のアンインストールが完了したら後、は、次の操作を行います。  
  
1.  BizTalk Server 管理コンソールでは、すべての受信場所を削除し、トランスポートの種類が MLLP の受信場所のトランスポートの種類を変更または別の型への送信ポートまたはポートを送信します。  
  
2.  管理コンソールで、MLLP アダプターを削除します。  
  
3.  ホスト インスタンスを再起動します。  
  
## <a name="btahl7-cannot-be-uninstalled-if-biztalk-server-has-already-been-uninstalled"></a>BizTalk Server が既にアンインストールされている場合は、BTAHL7 をアンインストールすることはできません。  
  
### <a name="symptom"></a>現象  
 アンインストール[!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]次のエラーが発生します。  
  
`A network error while attempting to read from file C:\Windows\Installer\Microsoft BizTalk <version\> Accelerator for HL7.msi`
  
**考えられる原因**:[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]のアンインストールの前にアンインストールされました[!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]しようとしました。 アンインストールする必要があります[!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]アンインストールする前に[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]します。  
  
**解像度**:再インストール[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]をアンインストールして[!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]、し、アンインストール[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]します。  
  
## <a name="messages-are-still-sent-after-the-applicable-mllp-send-port-has-been-stopped"></a>MLLP 送信ポートが停止した後、メッセージは送信もされます。  
  
### <a name="symptom"></a>現象  
 した後、MLLP 送信ポート、送信ポート経由で送信されたメッセージの停止が停止しないを引き続き送信されます。  
  
**考えられる原因**:送信ポートを停止すると、BizTalk ホストを停止することで削除されるまで確立された接続は残ります。 その結果、送信ポートが停止した後、メッセージは送信も。 これには、Biztalk Server の起動または送信ポートの停止中に呼び出し、MLLP アダプターを行わないために発生します。 BizTalk Server は、開始およびホスト サービスの停止中にのみ、MLLP アダプターを呼び出します。  
  
**解像度**:接続を削除して、停止する送信ポートの送信ハンドラーのホスト インスタンスを停止することで、メッセージの送信を停止することができます。 ただし、そのホスト インスタンスを停止すると停止したくないその他のメッセージが影響する可能性があります。 ケースであることがわかっている場合、作成するときに異なる方法で送信ポートを構成する必要があります。 この MLLP 送信ポートのみ (または、送信ポートのサブセット) の送信ハンドラーとして機能する別のホスト インスタンスを作成する必要があります。 このホスト インスタンスを停止することで、この送信ポートからメッセージの送信を停止できます。 影響はありません他の送信ハンドラーを使用するその他の送信ポートの他のメッセージの送信。  
  
## <a name="see-also"></a>参照  
 [HL7 のトラブルシューティングと既知の問題](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-and-known-issues-in-hl7.md)