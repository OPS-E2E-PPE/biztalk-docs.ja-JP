---
title: データベース Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77bc9390-cdb5-42ff-8b28-6265c51c79fc
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d5c0b1be12176653bba2414e32bdefbd83e9083
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013835"
---
# <a name="database-functoids"></a>データベース Functoid
**データベース**functoid は、出力インスタンス メッセージで使用するためのデータベースからデータを抽出します。 

## <a name="overview"></a>概要
一覧を次に、**データベース**functoid とその使用方法。  

- **データベース検索します。** 使用して、**データベース検索**functoid をデータベースから情報を抽出し、Microsoft ActiveX データ オブジェクト .NET (ADO.NET) レコード セットとして保存します。 この Functoid には、次の順序で 4 つの入力パラメーターが必要です。  

  -   参照値  

  -   データベース接続文字列  

  -   テーブル名  

  -   参照値の列の名前  

- **エラーの戻り値。** 使用して、**エラーを返す**functoid を実行時に行われる、データベース接続エラーなどのエラー情報を取得します。 この functoid には、1 つの入力パラメーターが必要です: からのリンク、**データベース検索**functoid。  

- **メッセージの書式設定します。** 引数の代入によって書式設定とローカライズが行われた文字列が返されます。また場合によっては、ID と値が返されます。  

- **アプリケーション ID を取得します。** アプリケーション オブジェクトの識別子を取得します。  

- **アプリケーション値を取得します。** アプリケーション値を取得します。  

- **共通 ID を取得します。** 共通オブジェクトの識別子を取得します。  

- **一般的な値を取得します。** 共通値を取得します。  

- **アプリケーション ID を削除します。** アプリケーション値を削除します。  

- **共通 ID を設定します。** 共通オブジェクトの識別子を設定して返します。  

- **値抽出します。** 使用して、**値抽出**functoid によって返されるレコード セット内の指定された列からデータを抽出する、**データベース検索**functoid。 この functoid は、2 つの入力パラメーターが必要です: へのリンク、**データベース検索**functoid と列の名前。  

  1 ~ 7、**データベース**functoid —**メッセージの書式設定、アプリケーション ID の取得**、**アプリケーション値の取得**、**共通 ID の取得**、 **共通値の取得**、**アプリケーション ID の削除**、および**共通 ID の設定**— は**CrossReferencing** functoid。 これらの Functoid は、入力メッセージの ID と値を、出力メッセージで必要とされる ID と値に変換します。 詳細については、次を参照してください。**データベース Functoid のリファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。 

## <a name="example"></a>例  
 次の例では、いくつか使用して、**データベース**functoid。 この例では、広範な地域に店舗を持つ大規模な小売メーカーを対象としています。 店舗を追跡するのに本社は各ストアという一意のコードを割り当てます、 **StoreID**します。 さらに、本社が互いに、次の情報を関連付けます**StoreID**:  

- StoreName  

- StoreAddress  

- City  

- PostalCode  

- StorePhoneNumber  

- StoreManager  

  この情報は、データベースに保存され、定期的に取引先に配布されます。 メーカー側では、すべての購入が店舗ではなく本社で行われます。 本社が取引先に注文書を送る場合、通常、複数の店舗が受け取る商品を 1 つの注文書で処理します。 商品を受け取る各店舗の名前とアドレス情報を送信する代わりに本社が単純に送信します、 **StoreID**します。 取引先が使用するには、高度な出荷通知には、名前とアドレス情報を挿入する、**データベース**functoid は、出力インスタンス メッセージにこの情報を自動的に挿入します。 次の図は、取引先がマップ内で StoreID の置換を実装する方法を示しています。  

  ![表示されている別のデータベース functoid をマップします。](../core/media/origdbfunctoids.gif "origdbfunctoids")  

  この図では、送信元スキーマは受信する注文書を表し、送信先スキーマは詳細な出荷通知を表しています。 **データベース検索**functoid が適切なデータベース テーブルから適切なレコードを検索します。 **値抽出**functoid は、参照レコードから適切な列を抽出します。 **エラーを返す**functoid は、実行時にエラー (接続の障害などがある場合は、エラー情報を含む文字列を出力します。  

  前の例では、最初の入力パラメーターから取得されます、 **StoreID**フィールドは、入力方向の注文書、および残りの 3 つの入力パラメーターが定数で構成されている、**構成\<Functoid\> Functoid**の ダイアログ ボックス、**データベース検索**functoid。 4 つの入力パラメーターすべての値を提供するために、送信元スキーマからのリンクを作成できます。  

> [!NOTE]
>  * など一部の Microsoft SQL Server データ型を使用することはできません**テキスト**、 **ntext**、および**イメージ**、参照値として、**データベース検索**functoid。 この Functoid には、テキスト文字列として表すことができるデータ型が必要です。  
>
>  * 入力パラメーターに一致する 1 つ以上のレコードがあるかどうか、**データベース検索**functoid、**値抽出**functoid は、最初のレコードからのみデータを抽出します。  
>
>  * 接続文字列で NT 認証を使用して、パスワードを暗号化で保護します。  

## <a name="available-functoids"></a>使用可能な functoid  
 **データベース**functoid には。 

* データベース検索
* エラー通知
* メッセージの書式設定
* アプリケーション ID の取得
* アプリケーション値の取得
* 共通 ID の取得
* 共通値の取得
* アプリケーション ID の削除
* 共通 ID の設定
* 値抽出

これらの functiods について詳しくは、次を参照してください。、 **Functoid リファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。

## <a name="see-also"></a>参照  
- [マップに基本 Functoid を追加する方法](../core/how-to-add-basic-functoids-to-a-map.md)   
- **データベース Functoid のリファレンス** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
