---
title: "チュートリアル: Oracle データベース アダプターの BizTalk プロジェクトの移行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a393219-bae8-4e08-acc8-76986600d0de
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0948e79b7f236bb20bbff9101195809bcc921a68
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-migrate-biztalk-projects-to-the-oracle-database-adapter"></a>チュートリアル: Oracle データベース アダプターを BizTalk プロジェクトを移行します。
Microsoft BizTalk Server に付属している Oracle データベースの BizTalk ODBC アダプターは WCF ベース異なります[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]など、多くの点で。  
  
-   デザイン時に、BizTalk プロジェクトを作成する操作。  
  
-   メタデータの取得エクスペリエンス。  
  
-   スキーマ ファイル名と名前空間。  
  
-   データは、マッピングを入力します。  
  
-   アダプターを使用して実行できる操作です。  
  
-   BizTalk Server 管理コンソールで物理ポートの構成  
  
 これらの相違点が含まれるトピックで説明した[を移行する BizTalk プロジェクトが作成を使用して BizTalk ODBC Adapter 用 Oracle Database](http://msdn.microsoft.com/library/18f40265-c7f3-44a1-99b6-1b1dc800561e)です。  
  
 ただし、Oracle データベースの BizTalk ODBC アダプターを使用して作成された BizTalk プロジェクトに変更を加えるし、WCF ベースで動作させるため[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
 このチュートリアルでは、Oracle データベースの BizTalk ODBC アダプターを使用して作成された既存の BizTalk プロジェクトに加える必要があります変更について説明します。  
  
> [!NOTE]
>  ここでは簡略化のため、このチュートリアルでは、ODBC 用 BizTalk アダプター Oracle データベースが参照されます「vPrev Oracle データベース アダプター」として 同様に、vPrev Oracle データベース アダプターを使用する BizTalk プロジェクトが参照されますとして「vPrev BizTalk プロジェクトです」  
  
## <a name="sample-used-for-the-tutorial"></a>チュートリアルでは、使用されるサンプル  
 このチュートリアルは、vPrev BizTalk プロジェクトを移行する方法を示すサンプル (Oracle_Migration) に基づいています。 サンプルが付属して Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)です。  
  
## <a name="prerequisites"></a>前提条件  
  
-   VPrev BizTalk プロジェクトが必要です。 このチュートリアルには、CUSTOMER テーブルで Insert 操作を実行する BizTalk プロジェクトが含まれます。 SCOTT スキーマの下で提供される SQL スクリプトを実行して、CUSTOMER テーブルが作成された、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]サンプルです。  
  
-   要求メッセージを vPrev Oracle データベース アダプターを使用して Oracle データベースで挿入操作を実行する必要があります。 要求メッセージは、vPrev Oracle データベース アダプターを使用して生成する挿入操作のスキーマに準拠している必要があります。  
  
-   内の手順を完了する必要があります[の前提条件](../../adapters-and-accelerators/adapter-oracle-database/prerequisites-to-create-oracle-database-applications.md) 
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトを理解します。  
 作成された vPrev BizTalk プロジェクトの主要な構成要素は次のとおりです。  
  
-   **BizTalk オーケストレーション**です。 これは、ポートの送信、Oracle を使用して Oracle データベースに要求メッセージの送信、受信ファイルの場所からの要求メッセージを取得し、応答を受信、別のファイルの場所に保存する簡単なオーケストレーションです。  
  
-   **Oracle データベースで実行する操作のスキーマ**です。 このチュートリアルには、SCOTT スキーマ内の CUSTOMER テーブルに対して挿入操作を実行する BizTalk プロジェクトが含まれます。 SCOTT スキーマの下で提供される SQL スクリプトを実行して、CUSTOMER テーブルが作成された、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]サンプルです。 顧客テーブルに対して生成されたスキーマは、CUSTOMERService_CUSTOMER_x5d.xsd です。 このスキーマは、vPrev Oracle データベース アダプターを使用して生成されます。  
  
    > [!NOTE]
    >  WCF ベースとは異なり[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]、vPrev Oracle データベース アダプターは、Oracle データベース テーブルで特定の操作を生成するメタデータをサポートしていません。 既定では、アダプターは、テーブルでサポートされるすべての操作のスキーマを生成します。 このような複数 vPrev Oracle データベース アダプターと WCF ベースの違いの[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[を移行する BizTalk プロジェクトが作成を使用して BizTalk ODBC Adapter 用 Oracle Database](http://msdn.microsoft.com/library/18f40265-c7f3-44a1-99b6-1b1dc800561e)です。  
  
-   **要求メッセージ**です。 顧客テーブルに挿入操作を実行する要求メッセージ。 要求メッセージのスキーマは、Oracle データベース アダプターの以前のバージョンで表示、挿入操作のスキーマに準拠しています。  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>BizTalk プロジェクトを移行する方法は、アダプターの以前のバージョンを使用して作成されました。  
 この移行チュートリアルの目的は、WCF ベースに準拠したメッセージを処理できるだけ WCF カスタム ポートを使用して、vPrev Oracle データベース アダプターによって生成されたスキーマに準拠した要求メッセージを送信するために[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。 そのため、簡単に言えば、移行練習では、WCF ベースに準拠していないメッセージを処理する WCF カスタム ポートを構成する[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]のスキーマです。  
  
 ただし、WCF カスタム ポートを適切に構成できるようにするには、次のタスクを実行する必要があります。  
  
-   SCOTT に対する挿入操作のメタデータを生成します。WCF ベースを使用して顧客テーブル[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
-   WCF ベースを使用する挿入操作を実行するための要求メッセージに vPrev Oracle データベース アダプターを使用して挿入操作を実行するための要求メッセージにマップ[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。  
  
-   WCF ベースを使用して受信した応答メッセージをマップ[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]vPrev Oracle データベース アダプターの応答メッセージにします。  
  
-   Wcf-custom Oracle を作成、BizTalk Server 管理コンソールのポートの送信受信します。  
  
-   要求と応答のマッピングを使用する WCF カスタム ポートを構成します。  
  
 
  
## <a name="see-also"></a>参照  
[Biztalk Server の概要](../../core/getting-started-with-biztalk-server.md)