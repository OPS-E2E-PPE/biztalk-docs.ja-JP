---
title: 手順 1:VPrev BizTalk プロジェクトで Oracle データベースの変更 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e3e22ac-126b-46ec-a6dc-3421ad721392
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba1acd612525615afe66b70446aaec99e4876bbf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376496"
---
# <a name="step-1-modify-the-vprev-biztalk-project-in-oracle-database"></a>手順 1:VPrev BizTalk プロジェクトで Oracle データベースを変更します。
![ステップ 1/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **所要時間:** 10 分  
  
 **目標:** この手順では、既存の vPrev BizTalk プロジェクトに、次の変更を行います。  
  
- SCOTT に対する挿入操作のメタデータを生成します。WCF ベースを使用して顧客テーブル[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  
- WCF ベースを使用して挿入操作を実行するための vPrev Oracle データベース アダプターは要求メッセージを使用して挿入操作を実行するための要求メッセージにマップ[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  
- WCF ベースを使用して受信応答メッセージにマップ[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]vPrev の Oracle データベース アダプターの応答メッセージにします。  
  
## <a name="prerequisites"></a>前提条件  
  
-   SCOTT の挿入操作を実行する vPrev BizTalk プロジェクトが必要です。Oracle データベースの CUSTOMER テーブル。  
  
## <a name="modify-the-vprev-biztalk-project"></a>VPrev BizTalk プロジェクトを変更します。  
  
1. SCOTT に対する挿入操作のメタデータを生成します。WCF ベースを使用して顧客テーブル[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。 使用することができます、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]メタデータを生成します。  
  
    メタデータを生成する方法の詳細については、次を参照してください。 [Visual Studio での Oracle データベース操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)します。 スキーマを生成すると後のような名前のファイル*OracleDBBindingSchema.xsd* BizTalk プロジェクトに追加されます。 このファイルには、SCOTT の挿入操作を実行するメッセージを送信するためのスキーマが含まれています。WCF ベースを使用して Oracle データベースの CUSTOMER テーブル[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  
2. 挿入操作のメタデータを生成すると、ポートのバインド ファイルも作成します。 次の手順で、Oracle データベースにメッセージを送信する Wcf-custom 送信ポートを作成するこのバインド ファイルが使用されます。 操作の SOAP アクションは、メタデータの生成対象の操作にも設定されます。 たとえば、挿入操作のメタデータを生成すると、送信ポートでの SOAP アクションで、操作名が、"Insert"になります。 ただし、操作名とオーケストレーションの一部異なる可能性があります、たとえば、作成した論理送信ポートで"Operation_1"。 その結果、送信ポートを使用して Oracle データベースにメッセージを送信するときにエラーが発生します。 これを回避するには、ことを確認しますで論理送信ポート、オーケストレーションでは、メタデータを生成する操作名と同じ操作名。  
  
    そのため、このチュートリアルが発生した場合、挿入操作のメタデータを生成するための名前を変更"Insert"する論理送信ポートの操作。  
  
3. 要求メッセージは、WCF ベースを使用して生成されたスキーマに vPrev Oracle データベース アダプターを使用して生成されたスキーマをマップ[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  
   1. BizTalk マッパーは、BizTalk プロジェクトに追加します。 BizTalk プロジェクトを右クリックし、[**追加**、] をクリック**新しい項目の**します。  
  
       **新しい項目の追加**ダイアログ ボックスで、左側のウィンドウから**マップ ファイル**します。 右側のウィンドウから次のように選択します。**マップ**します。 マップの名前を指定します。 **RequestMap.btm**します。 **[追加]** をクリックします。  
  
   2. 送信元スキーマ ペインで、次のようにクリックします。**ソース スキーマを開く**します。  
  
   3. **BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**vPrev の Oracle データベース アダプターの要求メッセージのスキーマを選択します。 このチュートリアルでは、次のように選択します。 *Oracle_Migration.CUSTOMERService_CUSTOMER_x5d*します。 **[OK]** をクリックします。  
  
   4. **送信元スキーマのルート ノード**ダイアログ ボックスで、*挿入* をクリック**OK**します。  
  
   5. 送信先スキーマ ペインで、次のようにクリックします。**送信先スキーマを開く**します。  
  
   6. **BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、WCF ベースの要求メッセージのスキーマを選択して[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。 このチュートリアルでは、次のように選択します。 *Oracle_Migration.OracleDBBindingSchema*します。 **[OK]** をクリックします。  
  
   7. **ターゲット スキーマのルート ノード**ダイアログ ボックスで、*挿入* をクリック**OK**します。  
  
   8. 次の図に示すように、両方のスキーマでは、それぞれの要素をマップします。  
  
       ![Oracle データベースに送信される要求をマップ](../../adapters-and-accelerators/adapter-oracle-database/media/4cb59338-40d1-4eb1-bd89-b5a3183959e1.gif "4cb59338-40d1-4eb1-bd89-b5a3183959e1")  
  
   9. マップを保存します。  
  
4. 応答メッセージは、WCF ベースを使用して生成されたスキーマに vPrev Oracle データベース アダプターを使用して生成されたスキーマをマップ[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  
   1. BizTalk マッパーは、BizTalk プロジェクトに追加します。 BizTalk プロジェクトを右クリックし、[**追加**、] をクリック**新しい項目の**します。  
  
       **新しい項目の追加**ダイアログ ボックスで、左側のウィンドウから**マップ ファイル**します。 右側のウィンドウから次のように選択します。**マップ**します。 マップの名前を指定します。 **ResponseMap.btm**します。 **[追加]** をクリックします。  
  
   2. 送信元スキーマ ペインで、次のようにクリックします。**ソース スキーマを開く**します。  
  
   3. **BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、WCF ベースの応答メッセージのスキーマを選択して[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。 このチュートリアルでは、次のように選択します。 *Oracle_Migration.OracleDBBindingSchema*します。 **[OK]** をクリックします。  
  
   4. **送信元スキーマのルート ノード**ダイアログ ボックスで、 *InsertResponse*  をクリック**OK**します。  
  
   5. 送信先スキーマ ペインで、次のようにクリックします。**送信先スキーマを開く**します。  
  
   6. **BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**vPrev の Oracle データベース アダプターの応答メッセージのスキーマを選択します。 このチュートリアルでは、次のように選択します。 *Oracle_Migration.CUSTOMERService_CUSTOMER_x5d*します。 **[OK]** をクリックします。  
  
   7. **ターゲット スキーマのルート ノード**ダイアログ ボックスで、 *InsertResponse*、順にクリックします**OK**します。  
  
   8. 表示になります WCF ベースに準拠した応答メッセージのスキーマ[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]追加を含む*InsertResult*要素。 スキーマとマップから削除する必要があります、 *InsertResponse*両方のスキーマ内の要素。  
  
       、**ツールボックス**、ドラッグ、**文字列左スペース削除**functoid し、マッパーのグリッドにドロップします。 接続、 **InsertResponse** functoid への送信元スキーマ内の要素。 同様に、接続、 **InsertResponse**を functoid に送信先スキーマ内の要素。 次の図は、functoid を使用して 2 つの要素をマップする方法を示しています。  
  
       ![Oracle データベースから受信した応答にマップする](../../adapters-and-accelerators/adapter-oracle-database/media/7fe18f5b-100f-4fe2-ac92-c111629d7fe9.gif "7fe18f5b-100f-4fe2-ac92-c111629d7fe9")  
  
      > [!NOTE]
      >  詳細については、次を参照してください。、**文字列左トリミング Functoid** [!INCLUDE[ui-guidance-developers-reference](../../includes/ui-guidance-developers-reference.md)]します。
  
   9. マップを保存します。  
  
5. 保存し、BizTalk ソリューションをビルドします。 クリックして、ソリューションを右クリックして**ソリューションのビルド**します。  
  
6. ソリューションを展開する。 クリックして、ソリューションを右クリックして**ソリューションの配置**します。  
  
## <a name="next-steps"></a>次の手順  
 Wcf-custom 送信ポートを作成および構成」の説明に従って、この手順で作成したマップを使用するように[手順 2。SQL アダプターを使用して Biztalk Server 管理コンソールでオーケストレーションを構成](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-orchestration-to-use-the-sql-adapter-in-biztalk-server.md)します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル: BizTalk プロジェクトの移行](https://msdn.microsoft.com/library/dd788186(v=bts.80).aspx)