---
title: Visual Studio に JD Edwards EnterpriseOne のスキーマのインポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 640d5884-953a-46b6-b9dc-b931392a3059
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be4fd488c762d69a85278af12ef21b25967ff3da
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382473"
---
# <a name="importing-schemas-into-biztalk-server-projects"></a>BizTalk Server プロジェクトへのスキーマのインポート
ここでは、JD Edwards EnterpriseOne サーバーのブラウズ、および [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクトへのスキーマのインポートについて説明します。  
  
> [!NOTE]
>  arglist を設定したことを確認する必要があります。 オーケストレーションでスキーマを生成する前に、jdearglist.txt を更新する必要があります。 詳細については、次を参照してください。[文字列値の処理](../core/handling-string-values2.md)します。  
  
> [!NOTE]
>  Jdearglist を変更するたびにそのビジネス オブジェクトのスキーマを再生成する必要があります。  
  
 JD Edwards EnterpriseOne ポートを作成後、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクトから Microsoft アダプター ウィザードを起動することで JD Edwards EnterpriseOne をブラウズできます。  
  
## <a name="import-schemas-into-visual-studio"></a>Visual Studio にスキーマをインポートします。
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]を開きます。  
  
2. 名前を右クリックし、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクトをポイントして、**追加**、選択と**生成した項目の追加**します。  
  
3. クリックして**追加**を開く、**アダプターの追加ウィザード**します。  
  
4. **アダプターの選択** ページで、スキーマをインポートするアダプターの名前を選択します (たとえば、 **JDEEnterpriseOne**)。  
  
5. **SQL Server**ボックスで、SQL server を選択します。  
  
6. **データベース**ボックスに、データベースを選択します。  
  
    既定のデータベースは、SQL サーバーと同じデータベースです。  
  
7. **ポート**ボックスで、SQL server を選択し、をクリックし、**次**します。  
  
    JD Edwards EnterpriseOne システムがブラウザーに表示されます。  
  
8. 以下に示す手順に進みます。  
  
   アダプターの追加ウィザードに、定義済みのすべてのシステムのツリーが表示されます。 JD Edwards EnterpriseOne には多くのモジュールがあります。 モジュールは名前の最初の 3 文字に従ってグループ化されます。  
  
- 階層の最初のレベルはモジュール名のすべての 3 文字プレフィックスのリストです。  
  
- 2 番目のレベルは同じ 3 文字プレフィックスを共有するすべてのモジュールのリストを示します。  
  
- 最後のレベルはモジュールに属するビジネス関数のリストを示します。 サービス アイコンを展開すると、サービスの操作を閲覧できます。  
  
  操作を展開すると、入出力引数が表示されます。 入出力引数を展開すると、引数のデータ型が表示されます。  
  
> [!NOTE]
>  サーバー オブジェクト定義が変更されると、スキーマを再生成し、そのデータを更新する必要があります。  
  
> [!NOTE]
>  スキーマの生成後に jdearglist.txt を変更した場合、スキーマを再生成してそのデータを更新する必要があります。 Jdearglist.txt の詳細については、次を参照してください。[文字列値の処理](../core/handling-string-values2.md)します。  
  
## <a name="select-the-schemas"></a>スキーマを選択します。  
  
1. **[インポートするサービス**] ページの最上位ノードを展開し、**ビジネス オブジェクト**ノードまたは**ビジネス サービス**ノード。  
  
2. クリックして、インポートする項目の横にあるチェック ボックスをオン**OK**します。  
  
3. 選択した JD Edwards EnterpriseOne の項目について生成されたスキーマが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクトにインポートされます。  
  
> [!NOTE]
>  AddressBook (N0100041) を使用する場合、フィールド名は**cActionCode**します。 アクションは XML ファイル自体の一部です。 コードは次のとおりです。  
  
-   A は追加 (Add) を表します。  
  
-   C は変更 (Change) を表します。  
  
-   D は削除 (Delete) を表します。  
  
-   I は問い合わせ (Inquiry) を表します。  
  
## <a name="next-step"></a>次の手順
[メッセージ コンテキストのプロパティの使用](../core/using-message-context-properties1.md)