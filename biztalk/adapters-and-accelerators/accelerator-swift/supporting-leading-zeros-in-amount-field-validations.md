---
title: 量のフィールドの検証時に先頭のゼロをサポートしている |Microsoft Docs
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
ms.openlocfilehash: e68cb3f776fd177bfaf437c6ae84b3e1da36f084
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529796"
---
# <a name="supporting-leading-zeros-in-amount-field-validations"></a>量のフィールドの検証時に先頭のゼロをサポートしています。
いくつかのメッセージの検証ポリシーは、高のフィールドの検証を実行します。 量のフィールドには先行ゼロを有効にするには、メッセージの種類の検証ポリシーを編集する必要があります。 既定の検証ポリシーの新しいバージョンを作成し、ビジネス ルール作成ツールの引数を編集またはポリシーを展開する前に、テキスト エディターで手動で既定のポリシーを編集することができます。  
  
 次の表では、有効または先行ゼロを無効にする方法を示します。 メソッドに設定する必要のある引数の序数も示します。 先行するゼロを有効にする場合は true または False を無効にするを設定します。  
  
|方法|引数の数|  
|------------|---------------------|  
|**CheckValidAmount**|6|  
|**CheckCurrencyAmount**|4|  
|**CheckValidSignCurrencyAmount**|3|  
|**CheckValidSignDateCurrencyAmount**|4|  
|**IsValidTransactionDetailsCurrencyAmount**|4|  
  
 上記の表の各メソッドは、1 つまたは複数のメッセージの検証ポリシーに含まれています。 ポリシーで、引数を設定するには、そのポリシーに含まれているかどうかを確認するメソッド名で検索する必要があります。 メソッドは、メッセージのポリシーで複数回を表示する場合があります。  
  
### <a name="to-enable-or-disable-leading-zeros"></a>有効または先行ゼロを無効にするには  
  
1.  メモ帳などのテキスト エディターを開きます。  
  
2.  エディターでは、有効または先行ゼロを無効にするメッセージの検証ポリシーの場所を参照します。 たとえば、見つかりますメッセージの検証ポリシー MT103_Validation_Policy.xml、MT103 メッセージの種類で*\<ドライブ\>*:/SWIFT/SWIFT メッセージのプログラム ファイルと Microsoft BizTalk Accelerator/カテゴリ 1/MT103 します。 検証ポリシーを開きます。  
  
3.  ポリシーでは、検索、 **CheckValidAmount**メソッド。  
  
4.  メソッドを検索する場合、適切な引数にカウント ダウンします。 たとえば、 **CheckValidAmount**メソッド、6 番目の引数までカウントします。 引数を設定**True**先頭のゼロまたは無効にする場合は False を有効にします。  
  
5.  前のテーブル内の各メソッドには、手順 3. および 4. を繰り返します。  
  
6.  ファイルを保存し、エディターを閉じます。