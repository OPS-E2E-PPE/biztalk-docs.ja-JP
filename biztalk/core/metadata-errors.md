---
title: メタデータ エラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ccb60c91-5905-4852-813b-586b82de4825
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07167c2c0189c36f7b1a321d81bd0070398953e8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975123"
---
# <a name="metadata-errors"></a>メタデータ エラー
診断と WCF メタデータのエラーの解決に関する情報。  
  
## <a name="error-consuming-wcf-service-metadata"></a>WCF サービスのメタデータを使用中にエラーが発生しました

|                 |                                   エラーの詳細                                    |
|-----------------|------------------------------------------------------------------------------------|
|  製品名   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 製品バージョン |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    イベント ID     |                                         0                                          |
|  イベント ソース   |                                         0                                          |
|    コンポーネント    |                                         0                                          |
|  シンボル名  |                                         0                                          |
|  メッセージ テキスト   |                        WCF サービスのメタデータを使用中にエラーが発生しました                        |
  
### <a name="explanation"></a>説明  
 このエラーは、サービスのメタデータが使用できないか、有効ではないことを示します。  
  
### <a name="user-action"></a>ユーザーの操作  
 サービスのメタデータを修正して使用します (使用する WCF サービスを所有している場合)。 サービス構成エディターに移動 (**svcConfigEditor.exe**)、構成ファイルを変更します。  それ以外の場合、サービス プロバイダーにお問い合わせください。

## <a name="failed-to-get-metadata"></a>メタデータを取得できませんでした

|                 |                                   エラーの詳細                                    |
|-----------------|------------------------------------------------------------------------------------|
|  製品名   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 製品バージョン |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    イベント ID     |                                         0                                          |
|  イベント ソース   |                                         0                                          |
|    コンポーネント    |                                         0                                          |
|  シンボル名  |                                         0                                          |
|  メッセージ テキスト   |                          メタデータを取得できませんでした"{0}                          |
  
## <a name="explanation"></a>説明  
 このエラーは、メタデータをそのサービスに使用できないことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 サービスに対してメタデータを有効にし、カスタマイズ ウィザードをもう一度実行します (使用する WCF サービスを所有している場合)。 それ以外の場合、サービス プロバイダーに問い合わせてください。