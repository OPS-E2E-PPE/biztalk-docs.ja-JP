---
title: 先行する量フィールドの検証時にゼロをサポートする |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- amounts, amount fields
- amounts, leading zeros
- validating, amount fields
ms.assetid: 7c202422-019f-43da-9c2a-4b9fdf0b2859
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3559b63ec7588fa2d7451779947a476cf19b7bf0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961368"
---
# <a name="supporting-leading-zeros-in-amount-field-validations"></a>先行する量フィールドの検証時にゼロをサポートします。
一部のメッセージ型の検証ポリシーは、金額のフィールドの検証を実行します。 金額フィールドには先行ゼロを有効にするには、メッセージの種類の検証ポリシーを編集する必要があります。 既定の検証ポリシーの新しいバージョンを作成して、ビジネス ルール作成ツールの引数を編集またはポリシーを展開する前に、のテキスト エディターで手動で既定のポリシーを編集することができます。  
  
 次の表は、有効にするにまたは先行ゼロを無効にする方法を示します。 メソッドに設定する必要がありますを指定する引数の序数も示します。 先行ゼロを有効にする場合は true または false に設定すると、それらを無効にするのを設定します。  
  
|方法|引数の数|  
|------------|---------------------|  
|**CheckValidAmount**|6|  
|**CheckCurrencyAmount**|4|  
|**CheckValidSignCurrencyAmount**|3|  
|**CheckValidSignDateCurrencyAmount**|4|  
|**IsValidTransactionDetailsCurrencyAmount**|4|  
  
 上記の表の各メソッドは、1 つまたは複数のメッセージ検証ポリシーに含まれます。 ポリシーで、引数を設定するには、そのポリシーがあるかどうかを確認するメソッドの名前で検索する必要があります。 メソッドは、メッセージのポリシーに複数回を表示することがあります。  
  
### <a name="to-enable-or-disable-leading-zeros"></a>有効にするにまたは先行ゼロを無効にするには  
  
1.  メモ帳などのテキスト エディターを開きます。  
  
2.  エディターで、有効にするにまたは先行ゼロを無効にするメッセージの検証ポリシーの場所を参照します。 たとえば、メッセージ検証ポリシー用あります MT103 メッセージの種類、MT103_Validation_Policy.xml で*\<ドライブ\>*:/プログラム ファイル/BizTalk Accelerator for SWIFT/SWIFT メッセージ/カテゴリ 1/MT103 です。 検証ポリシーを開きます。  
  
3.  ポリシーでの検索、 **CheckValidAmount**メソッドです。  
  
4.  メソッドを検索する場合、適切な引数をカウント ダウンします。 たとえば、 **CheckValidAmount**メソッド、6 番目の引数をカウントします。 引数に設定**True**を先頭にゼロまたはそれらを無効にする場合は False を有効にします。  
  
5.  上記の表の各メソッドを手順 3. および 4. を繰り返します。  
  
6.  ファイルを保存し、エディターを閉じます。