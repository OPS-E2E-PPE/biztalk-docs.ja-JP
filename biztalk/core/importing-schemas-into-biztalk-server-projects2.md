---
title: "BizTalk Server Projects2 へのスキーマのインポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- importing schemas
- schemas, importing into BizTalk Server projects
ms.assetid: 640d5884-953a-46b6-b9dc-b931392a3059
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ebb0a39850029adec06986da5ddad1fc44c33ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="importing-schemas-into-biztalk-server-projects"></a>BizTalk Server プロジェクトへのスキーマのインポート
ここでは、JD Edwards EnterpriseOne サーバーのブラウズ、および [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクトへのスキーマのインポートについて説明します。  
  
> [!NOTE]
>  arglist を設定したことを確認する必要があります。 オーケストレーションでスキーマを生成する前に、jdearglist.txt を更新する必要があります。 詳細については、次を参照してください。[文字列値の処理](../core/handling-string-values2.md)です。  
  
> [!NOTE]
>  Jdearglist を変更するたびにそのビジネス オブジェクトのスキーマを再生成する必要があります。  
  
 JD Edwards EnterpriseOne ポートを作成後、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクトから Microsoft アダプター ウィザードを起動することで JD Edwards EnterpriseOne をブラウズできます。  
  
### <a name="to-import-schemas-into-a-biztalk-server-project"></a>BizTalk Server プロジェクトにスキーマをインポートするには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]を開きます。  
  
2.  名前を右クリックし、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクトをポイントし、**追加**を選択して**生成した項目の追加**です。  
  
3.  をクリックして**追加**を開くには、**アダプターの追加ウィザード**です。  
  
4.  **アダプターの選択** ページで、スキーマをインポートするアダプターの名前を選択して (たとえば、 **JDEEnterpriseOne**)。  
  
5.  **SQL Server**ボックスで、SQL server を選択します。  
  
6.  **データベース**ボックスで、データベースを選択します。  
  
     既定のデータベースは、SQL サーバーと同じデータベースです。  
  
7.  **ポート**ボックスで SQL サーバーを選択し、をクリックして**次**です。  
  
     JD Edwards EnterpriseOne システムがブラウザーに表示されます。  
  
8.  以下に示す手順に進みます。  
  
 アダプターの追加ウィザードに、定義済みのすべてのシステムのツリーが表示されます。 JD Edwards EnterpriseOne には多くのモジュールがあります。 モジュールは名前の最初の 3 文字に従ってグループ化されます。  
  
-   階層の最初のレベルはモジュール名のすべての 3 文字プレフィックスのリストです。  
  
-   2 番目のレベルは同じ 3 文字プレフィックスを共有するすべてのモジュールのリストを示します。  
  
-   最後のレベルはモジュールに属するビジネス関数のリストを示します。 サービス アイコンを展開すると、サービスの操作を閲覧できます。  
  
 操作を展開すると、入出力引数が表示されます。 入出力引数を展開すると、引数のデータ型が表示されます。  
  
> [!NOTE]
>  サーバー オブジェクト定義が変更されると、スキーマを再生成し、そのデータを更新する必要があります。  
  
> [!NOTE]
>  スキーマの生成後に jdearglist.txt を変更した場合、スキーマを再生成してそのデータを更新する必要があります。 Jdearglist.txt の詳細については、次を参照してください。[文字列値の処理](../core/handling-string-values2.md)です。  
  
### <a name="to-select-the-schemas"></a>スキーマを選択するには  
  
1.  **[インポートするサービス**] ページの最上位のノードを展開し、**ビジネス オブジェクト**ノードまたは**ビジネス サービス**ノード。  
  
2.  インポート、およびをクリックする項目の横にチェック ボックスをオンに**OK**です。  
  
3.  選択した JD Edwards EnterpriseOne の項目について生成されたスキーマが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクトにインポートされます。  
  
> [!NOTE]
>  AddressBook (N0100041) を使用する場合、フィールド名は**cActionCode**です。 アクションは XML ファイル自体の一部です。 コードは次のとおりです。  
  
-   A は追加 (Add) を表します。  
  
-   C は変更 (Change) を表します。  
  
-   D は削除 (Delete) を表します。  
  
-   I は問い合わせ (Inquiry) を表します。  
  
## <a name="see-also"></a>参照  
 [JD Edwards EnterpriseOne 送信ハンドラーの作成](../core/creating-jd-edwards-enterpriseone-send-handlers.md)