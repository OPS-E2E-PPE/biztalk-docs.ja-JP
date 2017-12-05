---
title: "作成し、TIBCO でスキーマの使用 |Microsoft ドキュメント"
description: "BizTalk エディターを使用してスキーマを作成する、BizTalk adapter for TIBCO Enterprise Message Service とターゲットの名前空間をスキーマの BizTalk Server の設定"
ms.custom: 
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3927b0b3-db3b-4494-b003-d930af734e58
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 384d140832c123f46ecf531e64b3c1ca11e64f4e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="create-and-use-tibco-schemas"></a>作成し、TIBCO スキーマを使用

## <a name="overview"></a>概要
Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) で使用するスキーマは、XML エディターまたは Visual Studio の BizTalk Server エディター (オーケストレーションでアダプターを使用する場合のみ) を使用して作成します。 スキーマには、想定している情報の種類を記述します。 このトピックの情報は、送信ハンドラーと受信ハンドラーの両方に適用されます。  
  
BizTalk Adapter for TIBCO Enterprise Message Service で使用するスキーマを作成するときは、ターゲットの名前空間を含める必要があります。 BizTalk Server でターゲットの名前空間が必要なのは、特定のメッセージ インスタンスを特定のオーケストレーションに関連付けるキーとなるからです。 つまり、オーケストレーションでは特定のターゲットの名前空間を持つメッセージをサブスクライブし、そのターゲットの名前空間を持つ受信 XML メッセージが、メッセージをサブスクライブしたすべてのオーケストレーションに配信されます。 XML ドキュメント スキーマにターゲットの名前空間がない場合は、ルート要素の名前がキーとして使用されます。  

次の手順では、ターゲットの名前空間を設定する方法と、スキーマを生成する方法を示します。  
  
## <a name="generate-a-schema"></a>スキーマを生成します。    
 
1.  BizTalk エディターで、プロジェクトを開きます。  
  
2.  ソリューション エクスプ ローラーで右上で、で **追加**、し、**生成した項目の追加**です。  
  
3.  **テンプレート**ペインで、**スキーマの生成**、クリックして**追加**です。  
  
4.  **スキーマの生成**] ダイアログ ボックスで、**ドキュメントの種類**一覧で、[**整形式 XML**です。  
  
5.  をクリックして**参照**をクリックして、スキーマを生成する入力ファイルを検索する**OK**。  
  
次に、ターゲットの名前空間を設定します。  
  
## <a name="set-the-target-namespace"></a>ターゲットの名前空間を設定します。  
  
1.  BizTalk エディターで開き、スキーマ ファイルを右クリックして**\<スキーマ\>**、し、**プロパティ**です。  
  
2.  **プロパティ** ウィンドウで、検索、 **Namespace**フィールド名を入力、たとえば、`testNameSpace`です。  
  
 これで、メッセージを使用してオーケストレーションを継続できます。 メッセージが取得されると、ターゲットの名前空間が設定されたスキーマを使用するオーケストレーションが BizTalk Server で検索され、オーケストレーション プロセスが実行されます。  
  
## <a name="see-also"></a>参照  
 [アプリケーションの開発](../core/developing-applications5.md)