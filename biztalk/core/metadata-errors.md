---
title: メタデータ エラー |Microsoft ドキュメント
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
ms.openlocfilehash: 4dce5fc9eb944eccbeed57073c2546f81825ec6f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262946"
---
# <a name="metadata-errors"></a>メタデータ エラー
診断および WCF のメタデータ エラーを解決するための情報です。  
  
## <a name="error-consuming-wcf-service-metadata"></a>WCF サービスのメタデータを使用中にエラーが発生しました

||エラーの詳細|  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|WCF サービスのメタデータを使用中にエラーが発生しました|  
  
### <a name="explanation"></a>説明  
 このエラーは、サービスのメタデータが使用できないか、有効ではないことを示します。  
  
### <a name="user-action"></a>ユーザーの操作  
 サービスのメタデータを修正して使用します (使用する WCF サービスを所有している場合)。 サービス構成エディターに移動 (**svcConfigEditor.exe**) して、構成ファイルを変更します。  それ以外の場合、サービス プロバイダーに問い合わせてください。

## <a name="failed-to-get-metadata"></a>メタデータを取得できませんでした

||エラーの詳細|  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|"{0}" からメタデータを取得できませんでした。|  
  
## <a name="explanation"></a>説明  
 このエラーは、メタデータをそのサービスに使用できないことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 サービスに対してメタデータを有効にし、カスタマイズ ウィザードをもう一度実行します (使用する WCF サービスを所有している場合)。 それ以外の場合、サービス プロバイダーに問い合わせてください。