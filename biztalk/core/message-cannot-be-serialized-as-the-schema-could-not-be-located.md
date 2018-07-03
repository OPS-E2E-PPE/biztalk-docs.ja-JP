---
title: スキーマが見つからなかったために、メッセージがシリアル化ことはできません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 37897c04-650d-4695-846d-b8ba61365647
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f366fc619ac070d618345ce6bde9996710b1242
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988187"
---
# <a name="message-cannot-be-serialized-as-the-schema-could-not-be-located"></a>スキーマが見つからなかったため、メッセージをシリアル化できません
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                          |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                            |
| 製品バージョン |                                        [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                        |
|    イベント ID     |                                                                    -                                                                     |
|  イベント ソース   |                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                          |
|    コンポーネント    |                                                                EDI エンジン                                                                |
|  シンボル名  |                                              MessageSerializationFailureDueToMissingSchema                                               |
|  メッセージ テキスト   | メッセージがスキーマとしてシリアル化しないできる{0}配置されていることができませんでした。 スキーマが展開されていないか、複数のコピーが展開されています。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、インターチェンジのシリアル化に使用するために必要なスキーマを確認できなかったため、送信パイプラインで送信インターチェンジをシリアル化できなかったことを示します。 スキーマが展開されていないか、スキーマの複数のコピーが展開されています。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のいずれかの操作を行います。  
  
1.  インターチェンジに関連付けられたスキーマが展開されていない場合は、Visual Studio を開き、BizTalk プロジェクトにスキーマを追加してから、プロジェクトをビルドして展開します。  
  
2.  スキーマの複数のコピーが展開されている場合は、Visual Studio を開き、インターチェンジに関連付けられたスキーマの 1 つを残してその他すべてを展開解除します。