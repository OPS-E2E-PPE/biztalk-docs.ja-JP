---
title: SAP アダプターの BizTalk で使用する SAP RFC の作成の概要 |Microsoft ドキュメント
description: 作成、RFC では、RFC 変換先、および送信 SAP システム - BizTalk アダプター パック (BAP) の RFC
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 35937183-fc1e-49cd-8a75-8f62effe0013
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 802a2e33b8bc902dc784276ce7c1d9c3f37f3b12
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216522"
---
# <a name="create-and-send-an-rfc-in-sap"></a>作成および送信 RFC SAP
RFC を作成する SAP システムで完了する高度なタスクを一覧表示します。 各タスクには、非常に詳細な手順が含まれます。 その結果、これらのタスクを完了または SAP ガイダンスを参照してください、SAP 管理者に連絡をお勧めします。  
  
## <a name="create-an-rfc"></a>RFC を作成します。  
  
1.  SAP の GUI を起動します。  
  
2.  トランザクション SE37 に移動 (関数ビルダー) は、RFC 名を入力し、をクリックして**作成**です。  
  
3.  既存関数のグループでは、RFC が作成されるの RFC の簡単な説明を入力し、クリックして**保存**です。  
  
4.  **属性**] タブで、[、 **Remote-Enabled モジュール**ラジオ ボタンをクリックします。  
  
5.  **インポート** タブで、インポートのパラメーターを入力します。 これらのパラメーターは、関数モジュールに、外部データを渡すために使用されます。  
  
6.  **エクスポート** タブで、エクスポートのパラメーターを入力します。  
  
7.  **Changing**  タブを変化させるパラメーターを入力します。  
  
8.  **テーブル** タブで、テーブル名を入力します。  
  
9. **例外** タブで、エラーを処理する例外を入力します。  
  
10. **ソース コード** タブで、RFC のソース コード (ロジック) を入力します。  
  
11. クリックして、 **Activate**関数モジュールをアクティブ化するツールバーのアイコン。  

## <a name="create-an-rfc-destination"></a>RFC 変換先を作成します。  
  
1.  SAP の GUI を起動します。  
  
2.  トランザクション SM59 に移動 (表示および RFC 転送先の管理)。  
  
3.  メニュー バーからをクリックして**作成**です。  
  
4.  RFC 転送先の接続の種類、説明を入力し、Enter キーを押します。  
  
5.  選択、**登録済みサーバーのプログラム**ラジオ ボタン、プログラム ID、ゲートウェイのホスト、およびゲートウェイ サービスを入力します。  
  
6.  RFC 転送先を保存します。  

## <a name="send-an-rfc-from-an-sap-system"></a>SAP システムからの RFC を送信します。  
  
1.  SAP の GUI を起動します。  
  
2.  BD54 トランザクションを使用して論理システムを作成します。  
  
3.  SM59 トランザクションを使用して TCP/IP 接続で、RFC 変換先を作成します。  
  
4.  WE21 トランザクションを使用してポートを作成し、最後の手順で作成された RFC 転送先にアタッチします。  
  
5.  SE37 を使用して、RFC をトリガーします。 この RFC では、外部アプリケーションへの呼び出しし、そのアプリケーションからの応答を受信し、RFC を作成するためのロジックを含める必要があります。  
  
## <a name="see-also"></a>参照  
 [特定の SAP アダプターのシナリオを SAP GUI を使用したタスクを実行します。](performing-tasks-using-the-sap-gui-for-specific-sap-adapter-scenarios.md)