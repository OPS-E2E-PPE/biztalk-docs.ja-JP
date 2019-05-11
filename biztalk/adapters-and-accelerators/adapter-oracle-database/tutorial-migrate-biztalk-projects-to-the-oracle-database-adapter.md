---
title: チュートリアル:Oracle データベース アダプターを BizTalk プロジェクトの移行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a393219-bae8-4e08-acc8-76986600d0de
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1aca70228a53e88ab143820e3a6bf07409844392
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375889"
---
# <a name="tutorial-migrate-biztalk-projects-to-the-oracle-database-adapter"></a>チュートリアル:Oracle データベース アダプターを BizTalk プロジェクトを移行します。
Microsoft BizTalk Server に付属している Oracle データベースの BizTalk ODBC アダプターは WCF ベース異なります[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]など、多くの点で。  
  
- BizTalk プロジェクトの作成、デザイン時エクスペリエンス。  
  
- メタデータの取得エクスペリエンス。  
  
- スキーマ ファイル名と名前空間。  
  
- データ型のマッピング。  
  
- アダプターを使用して実行できる操作。  
  
- BizTalk Server 管理コンソールで物理ポートの構成  
  
  これらの相違点については、トピックで[を移行する BizTalk プロジェクト作成を使用して BizTalk ODBC Adapter for Oracle Database](http://msdn.microsoft.com/library/18f40265-c7f3-44a1-99b6-1b1dc800561e)します。  
  
  ただし、Oracle データベース、BizTalk ODBC アダプターを使用して作成された BizTalk プロジェクトに変更を加えるし、WCF ベースと連携させるため[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  
  このチュートリアルでは、Oracle データベース、BizTalk ODBC アダプターを使用して作成された既存の BizTalk プロジェクトにする必要があります変更について説明します。  
  
> [!NOTE]
>  説明を簡潔にするため、このチュートリアルでは、BizTalk ODBC Adapter for Oracle Database が参照されます「vPrev Oracle データベース アダプター」として 同様に、vPrev Oracle データベース アダプタを使用する BizTalk プロジェクトとして参照される「vPrev BizTalk プロジェクトです」  
  
## <a name="sample-used-for-the-tutorial"></a>このチュートリアルで使用されるサンプル  
 このチュートリアルは、vPrev BizTalk プロジェクトを移行する方法を示すサンプル (Oracle_Migration) に基づいています。 Microsoft とサンプルが提供される[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)します。  
  
## <a name="prerequisites"></a>前提条件  
  
- VPrev BizTalk プロジェクトが必要です。 このチュートリアルには、CUSTOMER テーブルの挿入操作を実行する BizTalk プロジェクトが含まれます。 SCOTT スキーマの下で提供される SQL スクリプトを実行して、CUSTOMER テーブルが作成された、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]サンプル。  
  
- VPrev Oracle データベース アダプターを使用して Oracle データベースに対して、挿入操作を実行する要求メッセージが必要です。 要求メッセージは、vPrev Oracle データベース アダプターを使用して生成する挿入操作のスキーマに準拠している必要があります。  
  
- 」の手順を完了する必要があります[の前提条件](../../adapters-and-accelerators/adapter-oracle-database/prerequisites-to-create-oracle-database-applications.md) 
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトを理解します。  
 作成された vPrev BizTalk プロジェクトの主要な構成要素は次のとおりです。  
  
- **BizTalk オーケストレーション**します。 これは、簡単なオーケストレーション ポートに送信しますが、Oracle を使用して Oracle データベースに要求メッセージの送信、受信ファイルの場所からの要求メッセージを取得し、応答を受信、ファイルの別の場所に保存します。  
  
- **Oracle データベースで実行する操作のスキーマを**します。 このチュートリアルには、SCOTT スキーマで顧客テーブルに挿入操作を実行する BizTalk プロジェクトが含まれます。 SCOTT スキーマの下で提供される SQL スクリプトを実行して、CUSTOMER テーブルが作成された、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]サンプル。 顧客テーブルに対して生成されたスキーマは、CUSTOMERService_CUSTOMER_x5d.xsd です。 VPrev Oracle データベース アダプターを使用して、このスキーマが生成されます。  
  
  > [!NOTE]
  >  WCF ベースとは異なり[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]vPrev の Oracle データベース アダプタが Oracle データベース テーブルで特定の操作のメタデータの生成をサポートしていません。 既定では、アダプターは、テーブルでサポートされているすべての操作のスキーマを生成します。 VPrev Oracle データベース アダプターと WCF ベースのはこのような違いの[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[を移行する BizTalk プロジェクト作成を使用して BizTalk ODBC Adapter for Oracle Database](http://msdn.microsoft.com/library/18f40265-c7f3-44a1-99b6-1b1dc800561e)します。  
  
- **要求メッセージ**します。 顧客テーブルに挿入操作を実行する要求メッセージ。 要求メッセージのスキーマは、Oracle データベース アダプターの以前のバージョンで表示、挿入操作のスキーマに準拠しています。  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>BizTalk プロジェクトを移行する方法は、アダプターの以前のバージョンを使用して作成されました。  
 この移行のチュートリアルの目的は WCF ベースに準拠したメッセージを処理できるだけ WCF カスタム ポートを使用して、vPrev Oracle データベース アダプターによって生成されたスキーマに準拠している要求メッセージを送信するために、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。 そのため、簡単に言えばの移行の練習では WCF ベースに準拠していないメッセージを処理する WCF カスタム ポートを構成する[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]のスキーマ。  
  
 ただし、WCF カスタム ポートを適切に構成できるようにするには、次のタスクを実行する必要があります。  
  
- SCOTT に対する挿入操作のメタデータを生成します。WCF ベースを使用して顧客テーブル[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  
- WCF ベースを使用して挿入操作を実行するための要求メッセージに vPrev Oracle データベース アダプターを使用して挿入操作を実行するための要求メッセージにマップ[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。  
  
- WCF ベースを使用して受信応答メッセージにマップ[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]vPrev Oracle データベース アダプターの応答メッセージにします。  
  
- Wcf-custom の Oracle を作成、BizTalk Server 管理コンソールのポートの送信-受信します。  
  
- 要求と応答のマッピングを使用する WCF カスタム ポートを構成します。  
  
 
  
## <a name="see-also"></a>参照  
[Biztalk Server の概要](../../core/getting-started-with-biztalk-server.md)