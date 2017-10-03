---
title: "作成して、スキーマを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- generating schemas
- schemas
- creating schemas
- schemas, generating
ms.assetid: 3927b0b3-db3b-4494-b003-d930af734e58
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f10275c5ed0b887907c7b26b7d1ce8ad5003b099
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-and-using-schemas"></a>作成して、スキーマの使用
Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) で使用するスキーマは、XML エディターまたは Visual Studio の BizTalk Server エディター (オーケストレーションでアダプターを使用する場合のみ) を使用して作成します。 スキーマには、想定している情報の種類を記述します。 このトピックの情報は、送信ハンドラーと受信ハンドラーの両方に適用されます。  
  
 BizTalk Adapter for TIBCO Enterprise Message Service で使用するスキーマを作成するときは、ターゲットの名前空間を含める必要があります。 BizTalk Server でターゲットの名前空間が必要なのは、特定のメッセージ インスタンスを特定のオーケストレーションに関連付けるキーとなるからです。 つまり、オーケストレーションでは特定のターゲットの名前空間を持つメッセージをサブスクライブし、そのターゲットの名前空間を持つ受信 XML メッセージが、メッセージをサブスクライブしたすべてのオーケストレーションに配信されます。 XML ドキュメント スキーマにターゲットの名前空間がない場合は、ルート要素の名前がキーとして使用されます。  
  
## <a name="generating-a-schema"></a>スキーマの生成  
 スキーマを生成する手順とターゲットの名前空間を設定する手順を次に示します。  
  
#### <a name="to-generate-a-schema-using-biztalk-editor"></a>BizTalk エディターを使用してスキーマを生成するには  
  
1.  BizTalk エディターで、プロジェクトを開きます。  
  
2.  ソリューション エクスプ ローラーで右上で、で **追加**、し、**生成した項目の追加**です。  
  
3.  **テンプレート**ペインで、**スキーマの生成**、クリックして**追加**です。  
  
4.  **スキーマの生成**] ダイアログ ボックスで、**ドキュメントの種類**一覧で、[**整形式 XML**です。  
  
5.  をクリックして**参照**をクリックして、スキーマを生成する入力ファイルを検索する**OK**。  
  
     次に、ターゲットの名前空間を設定する必要があります。  
  
#### <a name="to-set-the-target-namespace"></a>ターゲットの名前空間を設定するには  
  
1.  BizTalk エディターで開き、スキーマ ファイルを右クリックして**\<スキーマ >**、し、**プロパティ**です。  
  
2.  **プロパティ** ウィンドウで、検索、 **Namespace**フィールド名を入力、たとえば、`testNameSpace`です。  
  
 これで、メッセージを使用してオーケストレーションを継続できます。 メッセージが取得されると、ターゲットの名前空間が設定されたスキーマを使用するオーケストレーションが BizTalk Server で検索され、オーケストレーション プロセスが実行されます。  
  
## <a name="see-also"></a>参照  
 [アプリケーションの開発](../core/developing-applications5.md)