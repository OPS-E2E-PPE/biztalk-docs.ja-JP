---
title: 'チュートリアル 2: SAP RFC の BizTalk プロジェクトの移行 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migrating, BizTalk project from previous version of the SAP adapter
- migration
- migrating, SAP RFC BizTalk project
ms.assetid: b4943613-23d2-4869-b033-ec07daabfac5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80b5d53904b96267b1877310aa3480ce34a1bedc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218098"
---
# <a name="tutorial-2-migrating-an-sap-rfc-biztalk-project"></a>チュートリアル 2: SAP RFC の BizTalk プロジェクトを移行します。
Microsoft BizTalk Server に付属している SAP アダプターの以前のバージョンが WCF ベース異なる[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]など、多くの点で。  
  
-   デザイン時に、BizTalk プロジェクトを作成する操作。  
  
-   メタデータの取得エクスペリエンス。  
  
-   スキーマ ファイル名と名前空間。  
  
-   データは、マッピングを入力します。  
  
-   アダプターを使用して実行できる操作です。  
  
-   BizTalk Server 管理コンソールで物理ポートの構成。  
  
 これらの相違点が含まれるトピックで説明した[を移行する BizTalk プロジェクト作成を使用して、前のバージョンの SAP アダプター](http://msdn.microsoft.com/library/a486bac9-8952-43fd-8099-413f1491de37)です。  
  
 ただし、アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトに変更を加えるし、WCF ベースで動作させるため[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
 このチュートリアルでは、アダプターの以前のバージョンを使用して作成された既存の BizTalk プロジェクトに加える必要があります変更について説明します。  
  
> [!NOTE]
>  ここでは簡略化のため、このチュートリアルでは、SAP アダプターの以前のバージョンを vPrev SAP アダプターと呼びます。 同様に、vPrev SAP アダプターを使用する BizTalk プロジェクトが参照されます vPrev BizTalk プロジェクトです。  
  
## <a name="sample-used-for-the-tutorial"></a>チュートリアルでは、使用されるサンプル  
 このチュートリアルは、SAP システムで RFC を呼び出す vPrev BizTalk プロジェクトを移行する方法を示すサンプル (SAP_RFC_Migration) に基づいています。 サンプルが付属して、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)です。  
  
## <a name="prerequisites"></a>前提条件  
  
-   VPrev BizTalk プロジェクトが必要です。 このチュートリアルでは、BizTalk プロジェクトを SD_RFC_CUSTOMER_GET RFC を呼び出す必要があります。  
  
-   呼び出す vPrev SAP アダプターを使用して SD_RFC_CUSTOMER_GET RFC を実行する要求メッセージが必要です。 要求メッセージは、vPrev SAP アダプターを使用して生成された RFC のスキーマに準拠する必要があります。 このチュートリアルで提供されたサンプルには、この要求メッセージが含まれています。  
  
-   [厳密な名前キー ファイルを作成し、ツールの説明](../../adapters-and-accelerators/adapter-sap/prerequisites-to-create-sap-applications.md)
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトを理解します。  
 呼び出す RFC vPrev BizTalk プロジェクトの主要な構成要素は次のとおりです。  
  
-   **BizTalk オーケストレーション**です。 これは、ポートの送信、SAP を使用して SAP システムに要求メッセージの送信、受信ファイルの場所からの要求メッセージを取得し、応答を受信、別のファイルの場所に保存する簡単なオーケストレーションです。  
  
-   **スキーマの SAP システムで、呼び出し先 RFC**です。 このチュートリアルでは、BizTalk プロジェクトを SD_RFC_CUSTOMER_GET RFC を呼び出す必要があります。 RFC に対して生成されたスキーマは、SD_RFC_CUSTOMER_GET__x32003.xsd です。 このスキーマは、vPrev SAP アダプターを使用して生成されます。  
  
-   **要求メッセージ**です。 SD_RFC_CUSTOMER_GET RFC を起動する要求メッセージ。 要求メッセージのスキーマは vPrev SAP アダプター側に表示される、SD_RFC_CUSTOMER_GET RFC のスキーマに準拠しています。  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>BizTalk プロジェクトを移行する方法は、アダプターの以前のバージョンを使用して作成されました。  
 この移行チュートリアルの目的は、WCF ベースに準拠したメッセージを処理できるだけ WCF カスタム ポートを使用して、vPrev SAP アダプターによって生成されたスキーマに準拠した要求メッセージを送信するために[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 そのため、簡単に言えば、移行練習では、WCF ベースに準拠していないメッセージを処理する WCF カスタム ポートを構成する[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]のスキーマです。  
  
 ただし、WCF カスタム ポートを適切に構成できるようにするには、次のタスクを実行する必要があります。  
  
-   WCF ベースを使用して SD_RFC_CUSTOMER_GET RFC のメタデータを生成する[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
-   WCF ベースを使用して、RFC を呼び出すための要求メッセージに vPrev SAP アダプターを使用して、RFC を呼び出すための要求メッセージにマップ[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
-   WCF ベースを使用して受信した応答メッセージをマップ[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]vPrev SAP アダプターの応答メッセージにします。  
  
-   Wcf-custom SAP を作成する BizTalk Server 管理コンソールでポートを送信受信します。  
  
-   要求と応答のマッピングを使用する WCF カスタム ポートを構成します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [手順 1: RFC を呼び出すため vPrev BizTalk プロジェクトを変更します。](../../adapters-and-accelerators/adapter-sap/step-1-modify-the-vprev-biztalk-project-for-invoking-an-rfc.md)  
  
-   [手順 2: BizTalk Server 管理コンソールでオーケストレーションを構成します。](../../adapters-and-accelerators/adapter-sap/step-2-configure-the-orchestration-in-biztalk-server-administration-console1.md)  
  
-   [手順 3: 移行後のアプリケーションをテストします。](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application6.md)  
  
## <a name="see-also"></a>参照  
 [SAP アダプタ チュートリアル](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)