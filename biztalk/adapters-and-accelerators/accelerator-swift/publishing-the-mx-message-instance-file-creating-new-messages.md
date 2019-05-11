---
title: MX メッセージ インスタンス ファイル (新しいメッセージの作成) の発行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e7e6cdf4-b9db-42be-a92d-10a7471e2c2d
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f6375f61d484903b9359e2d3ab8723e6996d776
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377055"
---
# <a name="publishing-the-mx-message-instance-file-creating-new-messages"></a>MX メッセージ インスタンス ファイル (新しいメッセージの作成) の発行
**MX メッセージ インスタンスのファイルを発行するには。**  

1. 前の手順で生成された InfoPath フォーム テンプレートの出力フォルダーに移動して **.\\< MessageType\>\TemplateDS\InfoPath フォーム テンプレート**します。  

2. Internet Explorer で開く **http://localhost/sites/BASSite/New%20SWIFT%20MX%20Messages**します。  

3. 新しい Swift MX メッセージ ウィンドウで、クリックして**アップロード**します。  

4. ドキュメントのアップロード] ウィンドウで、[**参照**です。  

5. ファイルの選択 ダイアログ ボックスで、前の手順で生成された InfoPath フォームの出力フォルダーに移動 **.\\< MessageType\>\TemplateDS\InfoPath フォーム テンプレート**します。 選択、 \<MessageType\>.xml pacs.004.001.01.xml などのファイルをクリックして**オープン**します。  

6. ドキュメントのアップロード] ウィンドウで、[ **OK**です。  

7. 新しい SWIFT MX メッセージ。\<MessageType\>ウィンドウで、Namespace ボックスに「 <strong>http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMX_\<MessageType\></strong>、順にクリックします**OK**します。
