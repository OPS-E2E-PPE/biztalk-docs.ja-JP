---
title: '手順 1: vPrev BizTalk プロジェクトを SQL アダプターを使用しての変更 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 25ad959b-2818-47b8-9a09-3681abb75887
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2161520d1dba4ae070398668c53de2039e66e67d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979411"
---
# <a name="step-1-modify-the-vprev-biztalk-project-using-the-sql-adapter"></a>手順 1: vPrev BizTalk プロジェクトの SQL アダプタの使用を変更します。
![ステップ 1/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **所要時間:** 10 分  
  
 **目標:** この手順で、次を変更する既存の vPrev BizTalk プロジェクト。  
  
- WCF ベースを使用して、Customer テーブルに対する挿入操作のメタデータを生成[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
- WCF ベースを使用して挿入操作を実行するための要求メッセージに vPrev SQL アダプターを使用して挿入操作を実行するための要求メッセージにマップ[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
- WCF ベースを使用して受信応答メッセージにマップ[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]vPrev SQL アダプタを使用して受信した応答メッセージにします。  
  
## <a name="prerequisites"></a>前提条件  
 SQL Server データベースの Customer テーブルに対して挿入操作を実行する vPrev BizTalk プロジェクトが必要です。  
  
### <a name="to-modify-the-vprev-biztalk-project"></a>VPrev BizTalk プロジェクトを変更するには  
  
1. WCF ベースを使用して、Customer テーブルに対する挿入操作のメタデータを生成[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 使用することができます、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]メタデータを生成します。  
  
    メタデータを生成する方法の詳細については、[SQL アダプターを使用して Visual Studio での SQL Server 操作のメタデータの取得](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)を参照してください。 スキーマを生成すると後のような名前のファイル*TableOperation.dbo.Customer.xsd* BizTalk プロジェクトに追加されます。 このファイルには、WCF ベースを使用して SQL Server データベースの Customer テーブルに対して挿入操作を実行するメッセージを送信するためのスキーマが含まれています。[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
2. 挿入操作のメタデータを生成すると、ポートのバインド ファイルも作成します。 次の手順で、SQL Server データベースにメッセージを送信する Wcf-custom 送信ポートを作成するこのバインド ファイルが使用されます。 操作の SOAP アクションは、メタデータの生成対象の操作にも設定されます。 たとえば、挿入操作のメタデータを生成すると、送信ポートでの SOAP アクションで、操作名が、"Insert"になります。 ただし、操作名とオーケストレーションの一部異なる可能性があります、たとえば、作成した論理送信ポートで"Operation_1"。 その結果、送信ポートを使用して SQL Server データベースにメッセージを送信するときに、エラーが発生します。 これを回避するには、ことを確認しますで論理送信ポート、オーケストレーションでは、メタデータを生成する操作名と同じ操作名。  
  
    そのため、このチュートリアルが発生した場合、挿入操作のメタデータを生成するための名前を変更"Insert"する論理送信ポートの操作。  
  
3. 要求メッセージは、WCF ベースを使用して生成されたスキーマに vPrev SQL データベースのアダプターを使用して生成されたスキーマをマップ[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
   1. BizTalk マッパーは、BizTalk プロジェクトに追加します。 BizTalk プロジェクトを右クリックし、[**追加**、] をクリックし、**新しい項目の**します。  
  
       **新しい項目の追加**ダイアログ ボックスで、左側のウィンドウから**マップ ファイル**します。 右側のウィンドウから次のように選択します。**マップ**します。 マップの名前を指定します。 **RequestMap.btm**します。 **[追加]** をクリックします。  
  
   2. 送信元スキーマ ペインで、次のようにクリックします。**ソース スキーマを開く**します。  
  
   3. **BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、vPrev SQL アダプターの要求メッセージのスキーマを選択します。 このチュートリアルでは、次のように選択します。 *New_Migration.InsertCustomerService*、 をクリックし、 **OK**します。  
  
   4. **送信元スキーマのルート ノード**ダイアログ ボックスで、*挿入*、順にクリックします**OK**します。  
  
   5. 送信先スキーマ ペインで、次のようにクリックします。**送信先スキーマを開く**します。  
  
   6. **BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、WCF ベースの要求メッセージのスキーマを選択し、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 このチュートリアルでは、次のように選択します。 *New_Migration.TableOperation.dbo.Customer*、 をクリックし、 **OK**します。  
  
   7. **ターゲット スキーマのルート ノード**ダイアログ ボックスで、*挿入*、順にクリックします**OK**します。  
  
   8. 次の図に示すように、両方のスキーマでは、それぞれの要素をマップします。  
  
       ![要求スキーマのマッピング](../../adapters-and-accelerators/adapter-sql/media/850bbf52-fc3e-42c5-b879-51c6e39a502d.gif "850bbf52-fc3e-42c5-b879-51c6e39a502d")  
  
   9. マップを保存します。  
  
4. 応答メッセージは、WCF ベースを使用して生成されたスキーマに vPrev SQL アダプターを使用して生成されたスキーマをマップ[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。  
  
   1. BizTalk マッパーは、BizTalk プロジェクトに追加します。 BizTalk プロジェクトを右クリックし、[**追加**、] をクリック**新しい項目の**します。  
  
       **新しい項目の追加**ダイアログ ボックスで、左側のウィンドウから**マップ ファイル**します。 右側のウィンドウから次のように選択します。**マップ**します。 など、マップの名前を指定**ResponseMap.btm**、 をクリックし、**追加**します。  
  
   2. 送信元スキーマ ペインで、次のようにクリックします。**ソース スキーマを開く**します。  
  
   3. **BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、WCF ベースの応答メッセージのスキーマを選択し、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 このチュートリアルでは、次のように選択します。 *New_Migration.TableOperation.dbo.Customer*、 をクリックし、 **OK**します。  
  
   4. **送信元スキーマのルート ノード**ダイアログ ボックスで、 *InsertResponse*、順にクリックします**OK**します。  
  
   5. 送信先スキーマ ペインで、次のようにクリックします。**送信先スキーマを開く**します。  
  
   6. **BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、vPrev の応答メッセージのスキーマを選択し、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 このチュートリアルでは、次のように選択します。 *New_Migration.InsertCustomerService*、 をクリックし、 **OK**します。  
  
   7. **ターゲット スキーマのルート ノード**ダイアログ ボックスで、 *InsertResponse*、順にクリックします**OK**します。  
  
   8. 2 つのアダプターによって生成される応答スキーマの違いがいくつかがわかります。 これらの違いは、次のように説明できます。  
  
      - WCF ベースを使用して[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]レコードを挿入する場合は、操作、挿入の応答を主キーが含まれています (および、id フィールドでも) をテーブルに挿入された行の id フィールドの値を返します。 これは、WCF ベースに準拠した応答メッセージのスキーマ[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]追加が含まれています*InsertResult*要素。 この要素には、挿入された行の id フィールドを格納する配列が含まれています。  
  
      - VPrev を使用して[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]、応答メッセージの一部として空の「成功」要素をアダプターがのみを返します、テーブルにレコードを挿入する場合。  
  
        このような方法でスキーマをマップするする WCF ベースからの応答[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]id フィールドの値を含む「コピー」vPrev からの応答メッセージの一部である"Success"要素の一部として[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。 一括コピー functoid を使用して、別に 1 つのスキーマから要素をコピーすることができます。  
  
        一括コピー functoid を使用する、**ツールボックス**、一括コピー functoid をドラッグし、マッパーのグリッドにドロップします。 接続、 **InsertResult** functoid への送信元スキーマ内の要素。 同様に、接続、**成功**を functoid に送信先スキーマ内の要素。 次の図は、functoid を使用して 2 つの要素をマップする方法を示しています。  
  
        ![応答スキーマのマッピング](../../adapters-and-accelerators/adapter-sql/media/c4a347ae-8d2d-4357-b18d-37f36bef17c7.gif "c4a347ae-8d2d-4357-b18d-37f36bef17c7")  
  
      > [!NOTE]
      >  一括コピー functoid の詳細については、[ http://go.microsoft.com/fwlink/?LinkId=119749](http://go.microsoft.com/fwlink/?LinkId=119749)を参照してください。  
  
   9. マップを保存します。  
  
5. 保存し、BizTalk ソリューションをビルドします。 クリックして、ソリューションを右クリックして**ソリューションのビルド**します。  
  
6. ソリューションを展開する。 クリックして、ソリューションを右クリックして**ソリューションの配置**します。  
  
## <a name="next-steps"></a>次の手順  
 Wcf-custom 送信ポートを作成および構成」の説明に従って、この手順で作成したマップを使用するように[手順 2: SQL アダプターを使用して BizTalk Server 管理コンソールでオーケストレーションを構成](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-orchestration-to-use-the-sql-adapter-in-biztalk-server.md)します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 1: SQL アダプタを BizTalk プロジェクトを移行します。](../../adapters-and-accelerators/adapter-sql/tutorial-1-migrate-biztalk-projects-to-the-sql-adapter.md)