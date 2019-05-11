---
title: 認識できないメッセージの種類 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad4094bf-af00-4d5c-9661-7c8abcb1b722
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d1173304d39a0818f59aab990ef0b8f5412cb4e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292628"
---
# <a name="unrecognised-message-type"></a>認識されないメッセージの種類
## <a name="details"></a>詳細  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                                UnRecognizedMessageType                                 |
|  メッセージ テキスト   |                   認識されないメッセージの種類。 これ以上続行できません。                   |

## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、設定、そのインターチェンジのトランザクションのドキュメントの種類のドキュメント スキーマが展開されていない、または BizTalk Server が判断できないためで受信インターチェンジでした、受信パイプラインによって処理することを示しますトランザクションからドキュメントの種類は、識別子コード、バージョン、および名前空間を設定します。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のいずれかの操作を行います。  

- インターチェンジのトランザクション セットのドキュメントの種類のドキュメント スキーマをデプロイし、インターチェンジを再送信します。  

- 次の値が有効なスキーマを定義することを確認します。 x12 の場合、ターゲットの名前空間、バージョン/リリース、およびドキュメントを入力します。edifact では、ターゲットの名前空間、メッセージのバージョン番号、メッセージ リリース番号、およびメッセージを入力します。 詳細については、「パーティの解決、スキーマ探索、および受信した EDI メッセージの承認」のトピックの「スキーマ探索」セクションを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。
