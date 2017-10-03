---
title: "手順 1: vPrev Oracle データベースでの BizTalk プロジェクトを変更する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6e3e22ac-126b-46ec-a6dc-3421ad721392
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f8911a31eeec34a5508d29ff598a2f7624e5cd6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-modify-the-vprev-biztalk-project-in-oracle-database"></a>手順 1: vPrev Oracle データベースでの BizTalk プロジェクトを変更します。
![手順 1/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")  
  
 **所要時間:** 10 分  
  
 **目標:**このステップで、次を変更する既存の vPrev BizTalk プロジェクト。  
  
-   SCOTT に対する挿入操作のメタデータを生成します。WCF ベースを使用して顧客テーブル[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
-   WCF ベースを使用する挿入操作を実行するための要求メッセージに vPrev Oracle データベース アダプターを使用して挿入操作を実行するための要求メッセージにマップ[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
-   WCF ベースを使用して受信した応答メッセージをマップ[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]vPrev Oracle データベース アダプターの応答メッセージにします。  
  
## <a name="prerequisites"></a>前提条件  
  
-   VPrev BizTalk プロジェクト、SCOTT に Insert 操作を実行する権限が必要です。Oracle データベースの CUSTOMER テーブル。  
  
## <a name="modify-the-vprev-biztalk-project"></a>VPrev BizTalk プロジェクトを変更します。  
  
1.  SCOTT に対する挿入操作のメタデータを生成します。WCF ベースを使用して顧客テーブル[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。 使用することができます、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]メタデータを生成します。  
  
     メタデータを生成する方法については、次を参照してください。 [Visual Studio での Oracle データベース操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)です。 スキーマを生成すると後のような名前のファイルが*OracleDBBindingSchema.xsd*が BizTalk プロジェクトに追加します。 このファイルには、SCOTT に Insert 操作を実行するメッセージを送信するためのスキーマが含まれています。WCF ベースを使用して Oracle データベースの CUSTOMER テーブル[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
2.  挿入操作のメタデータを生成すると、ポートのバインド ファイルも作成されます。 次の手順でこのバインド ファイルは、Oracle データベースにメッセージを送信する Wcf-custom 送信ポートを作成する使用されます。 操作の SOAP アクションは、メタデータを生成する操作にも設定されます。 たとえば、挿入操作のメタデータを生成する場合、送信ポートでの SOAP アクションで、操作名されます"Insert"。 ただし、操作の名前、オーケストレーションの一部異なる場合があります、たとえばなどを作成する論理送信ポートで"Operation_1"。 結果として、送信ポートを使用して Oracle データベースにメッセージを送信するときに、エラーを取得します。 これを防ぐためには、確認の論理送信ポート、オーケストレーションでは、メタデータの生成対象の操作名と同じ操作名。  
  
     そのため、このチュートリアルが発生した場合、挿入操作のメタデータを生成するための名前を変更"Insert"への論理送信ポート操作します。  
  
3.  要求メッセージの WCF ベースを使用して生成されたスキーマに vPrev Oracle データベース アダプターを使用して生成されたスキーマにマップ[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
    1.  BizTalk マッパーは、BizTalk プロジェクトに追加します。 BizTalk プロジェクトを右クリックし、[**追加**、] をクリック**新しい項目の**します。  
  
         **新しい項目の追加**ダイアログ ボックスで、左ペインで、**マップ ファイル**です。 右側のウィンドウから次のように選択します。**マップ**です。 など、マップの名前を指定**RequestMap.btm**です。 **[追加]**をクリックします。  
  
    2.  送信元スキーマ ペインで、をクリックして**ソース スキーマを開く**です。  
  
    3.  **BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、vPrev Oracle データベース アダプターの要求メッセージのスキーマを選択します。 このチュートリアルでは、次のように選択します。 *Oracle_Migration.CUSTOMERService_CUSTOMER_x5d*です。 **[OK]**をクリックします。  
  
    4.  **送信元スキーマのルート ノード**ダイアログ ボックスで、*挿入* をクリック**OK**です。  
  
    5.  送信先スキーマ ペインで、をクリックして**送信先スキーマを開く**です。  
  
    6.  **BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、WCF ベースの要求メッセージのスキーマを選択して[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。 このチュートリアルでは、次のように選択します。 *Oracle_Migration.OracleDBBindingSchema*です。 **[OK]**をクリックします。  
  
    7.  **ターゲット スキーマのルート ノード**ダイアログ ボックスで、*挿入* をクリック**OK**です。  
  
    8.  次の図に示すように、両方のスキーマ内の各要素をマップします。  
  
         ![Oracle データベースに送信された要求をマップ](../../adapters-and-accelerators/adapter-oracle-database/media/4cb59338-40d1-4eb1-bd89-b5a3183959e1.gif "4cb59338-40d1-4eb1-bd89-b5a3183959e1")  
  
    9. マップを保存します。  
  
4.  応答メッセージは、WCF ベースを使用して生成されたスキーマに vPrev Oracle データベース アダプターを使用して生成されたスキーマにマップ[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
    1.  BizTalk マッパーは、BizTalk プロジェクトに追加します。 BizTalk プロジェクトを右クリックし、[**追加**、] をクリック**新しい項目の**します。  
  
         **新しい項目の追加**ダイアログ ボックスで、左ペインで、**マップ ファイル**です。 右側のウィンドウから次のように選択します。**マップ**です。 など、マップの名前を指定**ResponseMap.btm**です。 **[追加]**をクリックします。  
  
    2.  送信元スキーマ ペインで、をクリックして**ソース スキーマを開く**です。  
  
    3.  **BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、WCF ベースの応答メッセージのスキーマを選択して[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。 このチュートリアルでは、次のように選択します。 *Oracle_Migration.OracleDBBindingSchema*です。 **[OK]**をクリックします。  
  
    4.  **送信元スキーマのルート ノード**ダイアログ ボックスで、 *InsertResponse*  をクリック**OK**です。  
  
    5.  送信先スキーマ ペインで、をクリックして**送信先スキーマを開く**です。  
  
    6.  **BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、vPrev Oracle データベース アダプターの応答メッセージのスキーマを選択します。 このチュートリアルでは、次のように選択します。 *Oracle_Migration.CUSTOMERService_CUSTOMER_x5d*です。 **[OK]**をクリックします。  
  
    7.  **ターゲット スキーマのルート ノード**ダイアログ ボックスで、 *InsertResponse*、順にクリック**OK**です。  
  
    8.  わかります WCF ベースに準拠した応答メッセージのスキーマ[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]追加が含まれています*InsertResult*要素。 スキーマとマップから削除する必要があります、 *InsertResponse*両方のスキーマ内の要素。  
  
         そのためから、**ツールボックス**、ドラッグ、**文字列左スペース削除**functoid マッパー グリッドの上にドロップします。 接続、 **InsertResponse** functoid への送信元スキーマ内の要素。 同様に、接続、 **InsertResponse**を functoid に送信先スキーマ内の要素。 次の図は、functoid を使用して 2 つの要素をマップする方法を示しています。  
  
         ![Oracle データベースから受信した応答にマップする](../../adapters-and-accelerators/adapter-oracle-database/media/7fe18f5b-100f-4fe2-ac92-c111629d7fe9.gif "7fe18f5b-100f-4fe2-ac92-c111629d7fe9")  
  
        > [!NOTE]
        >  詳細については、次を参照してください。、**文字列左スペース削除 Functoid** [!INCLUDE[ui-guidance-developers-reference](../../includes/ui-guidance-developers-reference.md)]です。
  
    9. マップを保存します。  
  
5.  保存し、BizTalk ソリューションをビルドします。 ソリューションを右クリックし、をクリックして**ソリューションのビルド**です。  
  
6.  ソリューションを展開する。 ソリューションを右クリックし、をクリックして**ソリューションの配置**です。  
  
## <a name="next-steps"></a>次の手順  
 Wcf-custom 送信ポートを作成および構成」の説明に従って、この手順で作成したマップを使用するように[手順 2: SQL アダプターを使用して Biztalk Server 管理コンソールでオーケストレーションを構成する](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-orchestration-to-use-the-sql-adapter-in-biztalk-server.md)です。  
  
## <a name="see-also"></a>参照  
 [チュートリアル: BizTalk プロジェクトを移行します。](https://msdn.microsoft.com/library/dd788186(v=bts.80).aspx)