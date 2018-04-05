---
title: その他の問題のトラブルシューティング |Microsoft ドキュメント
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
ms.openlocfilehash: 796482df7234e2699b5b9bd3d1c12f6e98ccb923
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-other-issues"></a>その他の問題のトラブルシューティング
関連するその他の問題に対処[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]です。  
  
## <a name="message-rejected-by-the-btahl7-engine"></a>メッセージは、BTAHL7 エンジンによって拒否されました  
  
### <a name="symptom"></a>現象  
 メッセージは、メッセージ エンジンによってランダムに拒否されます。  
  
**考えられる原因**: HL7 標準に従って列挙値をテーブル 0338「L (& I)」の値が含まれています。 PRA セグメントのフィールドの 6 は、この値を含めることがあります。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] "&"の文字を扱う、区切り記号として、メッセージは拒否されます。  
  
**解像度**: この問題の 3 つの考えられる解決策があります。  
  
1.  メッセージ インスタンスで L\T\I 文字の組み合わせを使用するなど、エスケープ シーケンスを"&"の文字を処理します。  
  
2.  スキーマで PRA 6 で"LI"の列挙値を追加し、この値を代わりに、メッセージ インスタンスで使用します。  
  
3.  MSH2; でまったく異なるサブコンポーネント セパレーターを使用します。ただし、この特定のソリューションは、環境によっては現実的でない可能性があります。  
  
## <a name="cannot-edit-the-hl7-schema-using-visual-studio"></a>Visual Studio を使用して、HL7 スキーマを編集することはできません。  
  
### <a name="symptom"></a>現象  
 HL7 スキーマを使用して、編集できません[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。  
  
**考えられる原因**:[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]一部 HL7 スキーマをサポートしません。  
  
**解像度**: など他のエディターを使用して[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]メモ帳、HL7 スキーマを編集します。  
  
## <a name="message-handling-fails-with-no-errors-logged"></a>エラーの記録なしでメッセージの処理が失敗します。  
  
### <a name="symptom"></a>現象  
 システムは、エラー メッセージのログ記録または中断されたメッセージ キューでメッセージを配置することがなく、メッセージを処理します。  
  
**考えられる原因**: **HeaderSpecType**と**DocumentSpecType**プロパティの値は大文字小文字を区別します。 パイプラインを展開するときにこれらの名前の入力ミスにメッセージを手荒くし、エラーがログに記録なしで削除される可能性があります。  
  
**解像度**: を使用する場合は、大文字小文字の区別を観察、 **HeaderSpecType**と**DocumentSpecType**プロパティ値の名前。  
  
## <a name="message-header-fields-are-not-validated-correctly"></a>メッセージのヘッダー フィールドは正しく検証されていません  
  
### <a name="symptom"></a>現象  
 ヘッダー フィールドの検証に失敗しました。  
  
 理由:[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]シリアライザーは、実際のヘッダー フィールドのコンテキスト プロパティではなく、昇格されたプロパティを検証します。  
  
**考えられる原因**: ヘッダーから、オーケストレーションやマップに対応する昇格させたプロパティに変更が発生しました。  
  
**解像度**: のコンテキスト プロパティ メッセージ ヘッダー MSH1、MSH2、および MSH5 {1 ~ 3} は、データとの同期のように更新が必要です。  
  
## <a name="the-mllp-adapter-is-not-removed-during-uninstall"></a>アンインストール時に MLLP アダプターは削除されません。  
  
### <a name="symptom"></a>現象  
 BTAHL7 セットアップ プログラムは、BTAHL7 のアンインストール時に MLLP アダプターを削除できませんでした。  
  
**考えられる原因**: とトランスポートの種類が MLLP の受信場所または送信ポートが発生しました。 BizTalk Server プロジェクトのいずれかで参照されている場合、BTAHL7 セットアップは MLLP アダプターを削除できません。  
  
**解像度**: BTAHL7 のアンインストールが完了した後、次の操作します。  
  
1.  BizTalk Server 管理コンソールでは、すべての受信場所を削除し、トランスポートの種類が MLLP の受信場所のトランスポートの種類を変更または別の型に送信ポートまたはポートを送信します。  
  
2.  管理コンソールで、MLLP アダプターを削除します。  
  
3.  ホスト インスタンスを再起動します。  
  
## <a name="btahl7-cannot-be-uninstalled-if-biztalk-server-has-already-been-uninstalled"></a>BizTalk Server が既にアンインストールされている場合は、BTAHL7 をアンインストールすることはできません。  
  
### <a name="symptom"></a>現象  
 アンインストールする[!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]次のエラーが発生します。  
  
`A network error while attempting to read from file C:\Windows\Installer\Microsoft BizTalk <version\> Accelerator for HL7.msi`
  
**考えられる原因**:[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]のアンインストールの前にアンインストールされました[!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]しようとしました。 アンインストールする必要があります[!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]アンインストールする前に[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]です。  
  
**解像度**: を再インストール[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]、アンインストールしてから[!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]、し、アンインストール[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]です。  
  
## <a name="messages-are-still-sent-after-the-applicable-mllp-send-port-has-been-stopped"></a>該当する MLLP 送信ポートが停止した後、メッセージが送信されます。  
  
### <a name="symptom"></a>現象  
 した後は、停止、MLLP 送信ポート、送信ポート経由で送信されたメッセージが停止しないは、送信に進みます。  
  
**考えられる原因**: 送信ポートを停止すると、BizTalk ホストを停止することによって削除されるまで、接続が確立されているのままになります。 結果として、送信ポートが停止した後、メッセージは送信されます。 これは、Biztalk Server の開始または送信ポートの停止中に呼び出し MLLP アダプターを行わないために発生します。 BizTalk Server は、開始、ホスト サービスの停止中にのみ、MLLP アダプターを呼び出します。  
  
**解像度**: を停止する送信ポートの送信ハンドラーは、ホスト インスタンスを停止することによって接続と停止のメッセージの転送を削除することができます。 ただし、そのホスト インスタンスの停止を停止したくないその他のメッセージに影響する可能性があります。 大文字と小文字であることがわかっている場合、作成するときに異なる方法で、送信ポートを構成する必要があります。 この MLLP 送信ポートのみ (または、送信ポートのサブセット) の送信ハンドラーとして使用する別のホスト インスタンスを作成する必要があります。 このホスト インスタンスを停止することによってこの送信ポートからメッセージの送信を停止できます。 これは、影響しません他の送信ハンドラーを使用するその他の送信ポートでは、他のメッセージの送信。  
  
## <a name="see-also"></a>参照  
 [HL7 のトラブルシューティングと既知の問題](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-and-known-issues-in-hl7.md)