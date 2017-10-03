---
title: "Doctype が有効ではありません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 67233aae-65c0-4689-a4b3-60a48132343a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fec7dc4f2dfed0c8e8b8fcde13593d4e29997f7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="doctype-is-invalid"></a>Doctype が無効です
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|DocTypeInvalidFormat|  
|メッセージ テキスト|Doctype {0} が無効です。 1 つ以上の名前空間、バージョン、またはトランザクション セット ID を指定することはできません。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、スキーマが正しく検出されなかったため、EDI 受信パイプラインが受信インターチェンジを処理できなかったことを示します。  
  
 X12 の場合、ターゲットの名前空間は、[EDI のプロパティ] ダイアログ ボックスの [X12 インターチェンジ処理のプロパティ] ページの [カスタム トランザクション セットの定義を有効にします] グリッドで決定されます。 ターゲットの名前空間を正しく識別するには、メッセージの GS02 値および ST01 値が、グリッドの行のこれらの値と一致する必要があります。 トランザクション セットに使用されるスキーマの名前は、受信トランザクション セットのバージョン (GS08 の最初の 5 文字) と doctype (ST01) を、識別されたターゲットの名前空間に追加することで作成されます。  
  
 EDIFACT の場合、ターゲットの名前空間は、[EDI のプロパティ] ダイアログ ボックスの [EDIFACT インターチェンジ処理のプロパティ] ページの [カスタム トランザクション セットの定義を有効にします] グリッドで決定されます。 ターゲットの名前空間を正しく識別するには、メッセージの UNH2.1、UNH2.2、UNH2.3、UNH2.5、UNG2.1、および UNG2.2 の各値が、グリッドの行のこれらの値と一致する必要があります。 トランザクション セットに使用されるスキーマの名前は、受信トランザクション セットの UNH2.2 のメッセージ バージョン番号、UNH 2.3 のメッセージ リリース番号、および UNH2.1 のメッセージの種類を、識別されたターゲットの名前空間に追加することで作成されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のように操作を行います。  
  
1.  トランザクション セットのスキーマの名前空間は、[EDI のプロパティ] ダイアログ ボックスの [インターチェンジ処理のプロパティ] ページの [カスタム トランザクション セットの定義を有効にします] グリッドの行によって正しく識別されます。 正しく識別されない場合は、グリッドの値を変更します。  
  
2.  名前空間が正しく識別されている場合は、スキーマの識別に使用されている値が正しいかどうかを判断します。 X12 の場合、これらの値は、受信トランザクション セットのバージョン (GS08 の最初の 5 文字) および doctype (ST01) です。 EDIFACT の場合、受信トランザクション セットの UNH2.2 のメッセージ バージョン番号、UNH2.3 のメッセージ リリース番号、および UNH2.1 のメッセージの種類です。 これらの値が正しくない場合は、トランザクション セットの送信者に対して、これらのフィールドの値を変更し、メッセージを再送信するように依頼します。