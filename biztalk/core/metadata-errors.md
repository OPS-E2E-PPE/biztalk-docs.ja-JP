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
ms.openlocfilehash: a7699aa162044e13b5f3176e38cf858a5268e25f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65324942"
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
 このエラーは、サービスがないか、メタデータを示します使用できるか、無効です。  
  
### <a name="user-action"></a>ユーザーの操作  
 サービス メタデータを修正し、(使用する WCF サービスを所有) 場合を使用しようとします。 サービス構成エディターに移動 (**svcConfigEditor.exe**)、構成ファイルを変更します。  それ以外の場合、サービス プロバイダーにお問い合わせください。

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
 このエラーは、メタデータをそのサービスのご利用いただけませんを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 サービスのメタデータを有効にして、(使用する WCF サービスを所有) 場合は、使用ウィザードを再度実行します。 それ以外の場合、サービス プロバイダーに問い合わせてください。