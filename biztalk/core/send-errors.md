---
title: エラーを送信する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3cf61c82-ad48-4555-af53-fb841fd0f503
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76aa238227877ab70328e585d5d12b8c428e9061
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983325"
---
# <a name="send-errors"></a>送信エラー
診断および WCF の送信エラーを解決するための情報です。  
  
## <a name="failed-to-generate-odx-file"></a>ODX ファイルを生成できませんでした

|                 |                                   エラーの詳細                                    |
|-----------------|------------------------------------------------------------------------------------|
|  製品名   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 製品バージョン |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    イベント ID     |                                         0                                          |
|  イベント ソース   |                                         0                                          |
|    コンポーネント    |                                         0                                          |
|  シンボル名  |                                         0                                          |
|  メッセージ テキスト   |                            ODX ファイルを生成できませんでした                             |
  
### <a name="explanation"></a>説明  
 このエラーは、サービスの使用時にエラーが発生したことを示します。  
  
### <a name="user-action"></a>ユーザーの操作  
 サービスに有効な Web メソッドがあること、およびメタデータはホストされていることを確認します (WCF サービスを所有している場合)。 それ以外の場合、サービス プロバイダーに問い合わせてください。  
  
 WCF サービスの使用の詳細については、[に関する考慮事項ときに使用して WCF サービスを WCF 送信アダプタ](../core/considerations-when-consuming-wcf-services-with-the-wcf-send-adapters.md)を参照してください。
 
## <a name="response-message-body-was-not-read"></a>応答メッセージの本文を読み取れませんでした
  
|                 |                                        エラーの詳細                                        |
|-----------------|---------------------------------------------------------------------------------------------|
|  製品名   |     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]      |
| 製品バージョン |                 [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                  |
|    イベント ID     |                                              0                                              |
|  イベント ソース   |                                              0                                              |
|    コンポーネント    |                                              0                                              |
|  シンボル名  |                                              0                                              |
|  メッセージ テキスト   | 応答メッセージの本文を読み取れませんでした (接続が切断された可能性があります)。 |
  
### <a name="explanation"></a>説明  
 応答メッセージが返信される前に、クライアントの接続が解除された可能性があります。  
  
### <a name="user-action"></a>ユーザーの操作  
 クライアントの接続を確認します。 実行する手順と手順の範囲は、ポートの種類によって変わります。   
詳細については、[トラブルシューティングのために使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md)を参照してください。