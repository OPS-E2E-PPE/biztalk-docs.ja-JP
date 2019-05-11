---
title: SAP アダプターの BizTalk で使用する SAP の RFC の作成の概要 |Microsoft Docs
description: 作成、RFC と RFC 変換先、および BizTalk アダプター パック (BAP) の SAP システムから RFC を送信
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
ms.openlocfilehash: 4c05fb0b0c987c4f04115f6872056beeaf260355
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373538"
---
# <a name="create-and-send-an-rfc-in-sap"></a>作成し、SAP で RFC を送信
RFC を作成する SAP システムで完了する高度なタスクを一覧表示します。 各タスクには、非常に詳細な手順が含まれます。 その結果、これらのタスクを完了または SAP のガイダンスをご覧ください SAP 管理者に連絡をお勧めします。  
  
## <a name="create-an-rfc"></a>RFC を作成します。  
  
1.  SAP GUI を起動します。  
  
2.  トランザクション SE37 に移動 (関数ビルダー) は、RFC 名を入力し、をクリックして**作成**です。  
  
3.  既存関数のグループでは、RFC が作成される、RFC の短い説明を入力し、クリックして**保存**します。  
  
4.  **属性**] タブで、[、 **Remote-Enabled モジュール**ラジオ ボタンをクリックします。  
  
5.  **インポート** タブで、インポートのパラメーターを入力します。 これらのパラメーターは、関数モジュールを外部のデータを渡すために使用されます。  
  
6.  **エクスポート** タブで、エクスポートのパラメーターを入力します。  
  
7.  **Changing**  タブで、変化するパラメーターを入力します。  
  
8.  **テーブル**タブで、テーブル名を入力します。  
  
9. **例外** タブで、エラーを処理する例外を入力します。  
  
10. **ソース コード**タブで、RFC のソース コード (ロジック) を入力します。  
  
11. をクリックして、 **Activate**関数モジュールをアクティブ化するには、ツールバーのアイコン。  

## <a name="create-an-rfc-destination"></a>RFC 転送先を作成します。  
  
1.  SAP GUI を起動します。  
  
2.  トランザクション SM59 に移動 (表示し、RFC 転送先の管理)。  
  
3.  メニュー バーで、次のようにクリックします。**作成**です。  
  
4.  RFC 転送先の接続の種類、説明を入力し、Enter キーを押します。  
  
5.  選択、**登録済みサーバーのプログラム**オプション ボタンのプログラム ID、ゲートウェイ ホスト、およびゲートウェイ サービスを入力します。  
  
6.  RFC 転送先を保存します。  

## <a name="send-an-rfc-from-an-sap-system"></a>SAP システムから RFC を送信します。  
  
1.  SAP GUI を起動します。  
  
2.  BD54 トランザクションを使用して論理システムを作成します。  
  
3.  SM59 トランザクションを使用して TCP/IP 接続では、RFC 転送先を作成します。  
  
4.  WE21 トランザクションを使用してポートを作成し、最後の手順で作成された RFC 転送先にアタッチします。  
  
5.  SE37 を使用して、RFC をトリガーします。 この RFC では、RFC 外部アプリケーションへの呼び出しし、そのアプリケーションからの応答を受信するロジックを含める必要があります。  
  
## <a name="see-also"></a>参照  
 [特定の SAP アダプターのシナリオを SAP GUI を使用したタスクを実行します。](performing-tasks-using-the-sap-gui-for-specific-sap-adapter-scenarios.md)