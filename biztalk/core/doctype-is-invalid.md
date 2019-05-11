---
title: Doctype が無効です |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67233aae-65c0-4689-a4b3-60a48132343a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 316413265084e2df64bf2ef5c2e4227f9a886829
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530829"
---
# <a name="doctype-is-invalid"></a>Doctype が無効です。
## <a name="details"></a>詳細  
  
|                 |                                                                                                                 |
|-----------------|-----------------------------------------------------------------------------------------------------------------|
|  製品名   |               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                |
| 製品バージョン |                           [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                            |
|    イベント ID     |                                                        -                                                        |
|  イベント ソース   |             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI              |
|    コンポーネント    |                                                   EDI エンジン                                                    |
|  シンボル名  |                                              DocTypeInvalidFormat                                               |
|  メッセージ テキスト   | Doctype{0}が無効です。 1 つ以上の名前空間を決定することはできません、バージョン、またはトランザクション セット id |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、EDI が受信することを示します、スキーマが正しく検出されなかったため、パイプラインは、受信インターチェンジを処理できませんでした。  
  
 X12 の場合、ターゲットの名前空間が、X12 の"有効にするカスタム トランザクション セットの定義 グリッドで決定されます。 EDI のプロパティ ダイアログ ボックスのインターチェンジ処理のプロパティ ページ。 メッセージの GS02] と [ST01 の値は、ターゲットの名前空間を正しく識別するために、グリッドの行のこれらと一致する必要があります。 トランザクション セットに対して使用するスキーマの名前は、バージョン (GS08 の最初の 5 つの文字) と doctype (ST01) を受信トランザクション セット識別されたターゲット名前空間に追加することによって作成されます。  
  
 Edifact では、ターゲットの名前空間は、EDI のプロパティ ダイアログ ボックスの EDIFACT インターチェンジ処理のプロパティ ページの"有効にするカスタム トランザクション セットの定義 グリッドで決定されます。 メッセージの UNH2.1、UNH2.2、UNH2.3、UNH2.5、UNG2.1、および UNG2.2 の値は、ターゲットの名前空間を正しく識別するために、グリッドの行のこれらと一致する必要があります。 トランザクション セットに対して使用するスキーマの名前は、UNH2.2、UNH2.3 のメッセージ リリース番号、メッセージの種類 (unh2.1)、受信トランザクション セット識別されたターゲット名前空間でメッセージのバージョン番号を追加することによって作成されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のように操作を行います。  
  
1.  EDI のプロパティ ダイアログ ボックスの インターチェンジ処理のプロパティ ページの"有効にするカスタム トランザクション セットの定義 グリッド内の行で、トランザクション セットのスキーマの名前空間が正しく識別されていることを確認します。 それ以外の場合は、グリッド内の値を変更します。  
  
2.  名前空間を正しく指定されている場合は、スキーマの識別に使用される値が正しいかどうかを決定します。 X12 の場合、それらはバージョン (GS08 の最初の 5 つの文字) と受信トランザクション セット内の doctype (ST01) です。 EDIFACT の場合、サーバーは、UNH2.2、UNH2.3 のメッセージ リリース番号、メッセージの種類 (unh2.1)、受信トランザクション セットのメッセージ バージョン番号です。 値が正しくがない場合、そのフィールドの値を変更し、メッセージの再送信し、トランザクション セットの送信者があります。