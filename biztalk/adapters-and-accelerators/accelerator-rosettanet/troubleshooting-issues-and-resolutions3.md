---
title: 'トラブルシューティング: 問題と Resolutions3 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting
ms.assetid: 40f59f54-183e-43db-afb5-0a45b437697f
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad2e2db5e7d4d8c8181248f9345f1df2cca4a6dd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985099"
---
# <a name="troubleshooting-issues-and-resolutions"></a><span data-ttu-id="1b0d3-102">トラブルシューティング : 問題と解決策</span><span class="sxs-lookup"><span data-stu-id="1b0d3-102">Troubleshooting: Issues and Resolutions</span></span>
<span data-ttu-id="1b0d3-103">このトピックの「Microsoft® の実行に関連する問題に対処[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-103">This topic addresses issues related to running Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span> <span data-ttu-id="1b0d3-104">個々の問題について、具体的な現象、考えられる原因、および解決策について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-104">The individual issues detail a specific symptom, a possible cause, and a solution.</span></span>  
  
## <a name="error-publishing-a-batch-of-n-messages"></a><span data-ttu-id="1b0d3-105">"n" 通のメッセージのバッチ公開エラー</span><span class="sxs-lookup"><span data-stu-id="1b0d3-105">Error publishing a batch of "n" messages</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="1b0d3-106">現象</span><span class="sxs-lookup"><span data-stu-id="1b0d3-106">Symptom</span></span>  
 <span data-ttu-id="1b0d3-107">イベント ログに次のようなエラーが記録されます。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-107">You receive the following or similar error in the event log:</span></span>  
  
 <span data-ttu-id="1b0d3-108">メッセージング エンジンで、トランスポート アダプター "BizTalk HTTP Receiver" のメッセージ ボックス データベースに "n" 通のメッセージのバッチを公開中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-108">The Messaging Engine encountered an error publishing a batch of "n" messages to the Message Box database for the transport adapter "BizTalk HTTP Receiver".</span></span> <span data-ttu-id="1b0d3-109">このエラーの詳細については、「状態と動作状況の追跡ツール」を参照してください。また、エンドポイントのバインドが正しく構成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-109">Please refer to Health and Activity Tracking tool for more detailed information on this failure and check the endpoint bindings are correctly configured.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="1b0d3-110">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="1b0d3-110">Possible Cause</span></span>  
 <span data-ttu-id="1b0d3-111">このエラーは、次のいずれかの原因により起こる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-111">This error could be caused by one of the following reasons:</span></span>  
  
- <span data-ttu-id="1b0d3-112">暗号化解除証明書が紛失している。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-112">Missing decryption certificate</span></span>  
  
- <span data-ttu-id="1b0d3-113">メッセージが間違って暗号化されている。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-113">Incorrectly encrypted message</span></span>  
  
- <span data-ttu-id="1b0d3-114">メッセージが認証されていない (ソースが有効なパートナーとして認識されていない)。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-114">Unauthorized message (source not recognized as a valid partner)</span></span>  
  
- <span data-ttu-id="1b0d3-115">メッセージが、ヘッダー部位 (Preamble、Delivery Header、Service Header) のいずれかの検証に失敗している。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-115">Message failing validation of any header part: preamble, delivery header, or service header.</span></span>  
  
  <span data-ttu-id="1b0d3-116">このメッセージの前に、原因を詳細に示す別のエラー メッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-116">This message may be preceded by another error message that details the cause.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="1b0d3-117">解決方法</span><span class="sxs-lookup"><span data-stu-id="1b0d3-117">Solution</span></span>  
 <span data-ttu-id="1b0d3-118">エラー メッセージに記載されている詳細情報も確認してください。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-118">Review the details provided with the error message for additional help.</span></span> <span data-ttu-id="1b0d3-119">Microsoft の再起動[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]™ この問題を解決する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-119">Restarting Microsoft [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]™ may resolve this issue.</span></span>  
  
## <a name="you-cannot-unenlist-all-artifacts"></a><span data-ttu-id="1b0d3-120">一部のアイテムの登録を解除できない</span><span class="sxs-lookup"><span data-stu-id="1b0d3-120">You cannot unenlist all artifacts</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="1b0d3-121">現象</span><span class="sxs-lookup"><span data-stu-id="1b0d3-121">Symptom</span></span>  
 <span data-ttu-id="1b0d3-122">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Clean ユーティリティを実行しても、登録を解除できないアイテムが残ります。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-122">Running the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Clean utility does not unenlist all artifacts.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="1b0d3-123">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="1b0d3-123">Possible Cause</span></span>  
 <span data-ttu-id="1b0d3-124">実行する場合、 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Microsoft® 管理コンソール (MMC) からアグリーメントとパートナーを削除する前に Clean ユーティリティ BtarnClean ユーティリティできなくでも使用されますので、すべての成果物の参加を解除します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-124">If you run the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Clean utility before deleting agreements and partners from the Microsoft® Management Console (MMC), the BtarnClean utility will not be able to unenlist all artifacts because they are still used.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="1b0d3-125">解決方法</span><span class="sxs-lookup"><span data-stu-id="1b0d3-125">Solution</span></span>  
  
##### <a name="to-remove-artifacts-using-the-loopback-utility"></a><span data-ttu-id="1b0d3-126">Loopback ユーティリティを使用してアイテムを除去するには</span><span class="sxs-lookup"><span data-stu-id="1b0d3-126">To remove artifacts using the Loopback utility</span></span>  
  
1.  <span data-ttu-id="1b0d3-127">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-127">At the command prompt, type:</span></span>  
  
    ```  
    lookback.exe /disable <home org or partner>  
    ```  
  
2.  <span data-ttu-id="1b0d3-128">BtarnClean.exe ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-128">Run the BtarnClean.exe file.</span></span>  
  
3.  <span data-ttu-id="1b0d3-129">BizTalk エクスプローラーで、パーティを削除します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-129">In BizTalk Explorer, delete the parties.</span></span>  
  
## <a name="installing-btarn-on-a-computer-without-biztalk-server-causes-missing-files"></a><span data-ttu-id="1b0d3-130">BizTalk Server がインストールされていないコンピューターに BTARN をインストールするとファイルが欠落する</span><span class="sxs-lookup"><span data-stu-id="1b0d3-130">Installing BTARN on a computer without BizTalk Server causes missing files</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="1b0d3-131">現象</span><span class="sxs-lookup"><span data-stu-id="1b0d3-131">Symptom</span></span>  
 <span data-ttu-id="1b0d3-132">ない MicrosoftBizTalk サーバーまたは Microsoft を持たないコンピューターで結果が得られます ConfigFramework.exe ファイルを実行している[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]をインストールします。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-132">Running the ConfigFramework.exe file yields no results on a computer that does not have MicrosoftBizTalk Server or Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] installed.</span></span> <span data-ttu-id="1b0d3-133">この [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 構成は、HTTP クライアントとしてのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-133">You can only use this [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] configuration as an HTTP client.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="1b0d3-134">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="1b0d3-134">Possible Cause</span></span>  
 <span data-ttu-id="1b0d3-135">インストール先に 2 つの DLL ファイルが見つかりません。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-135">Two DLL files are missing from the installation.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="1b0d3-136">解決方法</span><span class="sxs-lookup"><span data-stu-id="1b0d3-136">Solution</span></span>  
 <span data-ttu-id="1b0d3-137">コンピューターに SQLXML をインストールしてから、[System] フォルダーに Msxml4.dll と Atl71.dll ファイルを手動でコピーします。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-137">Install SQLXML on the computer, and then manually copy the Msxml4.dll and Atl71.dll files to the System folder.</span></span>  
  
## <a name="you-receive-an-access-error-when-attempting-to-change-the-btarn-configuration"></a><span data-ttu-id="1b0d3-138">BTARN 構成を変更しようとすると、アクセス エラーが表示される</span><span class="sxs-lookup"><span data-stu-id="1b0d3-138">You receive an access error when attempting to change the BTARN configuration</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="1b0d3-139">現象</span><span class="sxs-lookup"><span data-stu-id="1b0d3-139">Symptom</span></span>  
 <span data-ttu-id="1b0d3-140">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理コンソールを使用して構成ファイルをインポートすると、次のようなエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-140">You receive the following error message when you import a configuration file using the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console:</span></span>  
  
 <span data-ttu-id="1b0d3-141">構成ストアから送信ポート 'RNSTT.Async' のプライマリ トランスポートに対して、トランスポートの種類のデータを格納できませんでした。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-141">Could not store transport type data for Primary Transport of Send Port 'RNSTT.Async' to config store.</span></span> <span data-ttu-id="1b0d3-142">アクセスが拒否されました。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-142">Access is denied.</span></span>  
  
 <span data-ttu-id="1b0d3-143">このエラー メッセージは、新しいパートナーを作成するなどして構成を変更しようとするときにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-143">You can also receive this error when you try to change the configuration, such as by creating a new partner.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="1b0d3-144">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="1b0d3-144">Possible Cause</span></span>  
 <span data-ttu-id="1b0d3-145">現在のユーザーが BizTalk Administrators グループのメンバではありません。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-145">The current user is not a member of the BizTalk Administrators group.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="1b0d3-146">解決方法</span><span class="sxs-lookup"><span data-stu-id="1b0d3-146">Solution</span></span>  
 <span data-ttu-id="1b0d3-147">現在のユーザーを BizTalk Administrators グループのメンバにします。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-147">Make sure that the current user is a member of the BizTalk Administrators group.</span></span>  
  
## <a name="you-receive-bam-errors"></a><span data-ttu-id="1b0d3-148">BAM エラーが発生する</span><span class="sxs-lookup"><span data-stu-id="1b0d3-148">You receive BAM errors</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="1b0d3-149">現象</span><span class="sxs-lookup"><span data-stu-id="1b0d3-149">Symptom</span></span>  
 <span data-ttu-id="1b0d3-150">イベント ビューアーに次のエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-150">You receive the following error messages in the Event Viewer:</span></span>  
  
 <span data-ttu-id="1b0d3-151">メッセージ アクティビティの追跡中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-151">Error happened in tracking Message activity.</span></span> <span data-ttu-id="1b0d3-152">エラー メッセージは "ストアド プロシージャが存在しません" です。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-152">Error message is Stored Procedure Does Not Exist.</span></span>  
  
 <span data-ttu-id="1b0d3-153">- または -</span><span class="sxs-lookup"><span data-stu-id="1b0d3-153">-or-</span></span>  
  
 <span data-ttu-id="1b0d3-154">Id の BAM メッセージ アクティビティの終了エラー  *\<ID 番号\>* します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-154">Error in terminating BAM message activity with id *\<ID number\>*.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="1b0d3-155">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="1b0d3-155">Possible Cause</span></span>  
 <span data-ttu-id="1b0d3-156">ビジネス アクティビティ監視 (BAM) 追跡ツールがインストールされていません。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-156">The Business Activity Monitoring (BAM) tracking tool is not installed.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="1b0d3-157">解決方法</span><span class="sxs-lookup"><span data-stu-id="1b0d3-157">Solution</span></span>  
 <span data-ttu-id="1b0d3-158">BAM 追跡ツールを使用してをインストール、**カスタム インストール**オプション。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-158">Install the BAM tracking tool using the **Custom Installation** option.</span></span> <span data-ttu-id="1b0d3-159">BAM 機能が不要な場合は、これらのメッセージを無視するか、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理コンソールを使用して追跡機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-159">If you do not need BAM functionality, you can ignore these messages or disable tracking using the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console.</span></span> <span data-ttu-id="1b0d3-160">追跡機能を無効にした後で、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] とインターネット インフォメーション サービス (IIS) を再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-160">After you disable tracking, you must restart [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and Internet and Information Services (IIS).</span></span>  
  
## <a name="your-xsd-schema-does-not-display-properly-in-biztalk-editor"></a><span data-ttu-id="1b0d3-161">BizTalk エディターに XSD スキーマが正しく表示されない</span><span class="sxs-lookup"><span data-stu-id="1b0d3-161">Your XSD Schema does not display properly in BizTalk Editor</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="1b0d3-162">現象</span><span class="sxs-lookup"><span data-stu-id="1b0d3-162">Symptom</span></span>  
 <span data-ttu-id="1b0d3-163">BizTalk エディターでスキーマの内容を正しく表示できません。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-163">You cannot view the content of a schema properly in BizTalk Editor.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="1b0d3-164">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="1b0d3-164">Possible Cause</span></span>  
 <span data-ttu-id="1b0d3-165">`displayroot_reference` 要素の `schemaInfo` 属性がスキーマにありません。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-165">The schema is missing the `displayroot_reference` attribute for the `schemaInfo` element.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="1b0d3-166">解決方法</span><span class="sxs-lookup"><span data-stu-id="1b0d3-166">Solution</span></span>  
 <span data-ttu-id="1b0d3-167">メモ帳などのテキスト エディターでスキーマを開き、`displayroot_reference` 属性を `schemaInfo` 要素に追加します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-167">Open the schema in Notepad or another text editor and add the `displayroot_reference` attribute to the `schemaInfo` element.</span></span> <span data-ttu-id="1b0d3-168">`displayroot_reference` 属性には、`root_reference` 属性と同じ値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-168">The value of the `displayroot_reference` attribute should be the same as the `root_reference` attribute.</span></span>  
  
 <span data-ttu-id="1b0d3-169">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-169">For example:</span></span>  
  
 <span data-ttu-id="1b0d3-170">\<schemaInfo document_type"4A1"バージョン = ="V02_00"xmlns ="<http://schemas.microsoft.com/BizTalk/2003>" *displayroot_reference ="Pip4A1StrategicForecastNotification"* root_reference"Pip4A1StrategicForecastNotification"を = \></span><span class="sxs-lookup"><span data-stu-id="1b0d3-170">\<schemaInfo document_type="4A1" version="V02_00" xmlns="<http://schemas.microsoft.com/BizTalk/2003>" *displayroot_reference="Pip4A1StrategicForecastNotification"* root_reference="Pip4A1StrategicForecastNotification" \></span></span>  
  
## <a name="404-not-found-error-when-sending-a-http-request"></a><span data-ttu-id="1b0d3-171">HTTP 要求の送信時に "404 Not found" というエラーが表示される</span><span class="sxs-lookup"><span data-stu-id="1b0d3-171">404 Not found error when sending a HTTP request</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="1b0d3-172">現象</span><span class="sxs-lookup"><span data-stu-id="1b0d3-172">Symptom</span></span>  
 <span data-ttu-id="1b0d3-173">HTTP 要求を送信すると、次のようなエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-173">You receive the following or similar errors when sending a HTTP request:</span></span>  
  
 <span data-ttu-id="1b0d3-174">リモート サーバーが (404) Not Found エラーを返しました。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-174">The remote server returned an error: (404) Not Found.</span></span>  
  
 <span data-ttu-id="1b0d3-175">メッセージが ../BTSHttpReceive.dll に送信されませんでした。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-175">Message cannot be sent to ../BTSHttpReceive.dll.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="1b0d3-176">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="1b0d3-176">Possible Cause</span></span>  
 <span data-ttu-id="1b0d3-177">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Internet Server API (ISAPI) の拡張 DLL (BTSHttpReceive.dll) がインターネット インフォメーション サービス (IIS) で構成されていません。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-177">The [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Internet Server API (ISAPI) extension DLL (BTSHttpReceive.dll) has not been configured in Internet Information Services (IIS).</span></span> <span data-ttu-id="1b0d3-178">これは、HwsMessages HttpReceive Web サービス拡張が構成されていないか、この Web サービス拡張が構成されていても、許可されていない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-178">This occurs if the HwsMessages HttpReceive web service extension is not configured and if this web service extension is configured, but not allowed.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="1b0d3-179">解決方法</span><span class="sxs-lookup"><span data-stu-id="1b0d3-179">Solution</span></span>  
 <span data-ttu-id="1b0d3-180">HwsMessages HttpReceive Web サービス拡張が構成されているかどうかを判断し、構成されていない場合に許可するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-180">To determine whether the HwsMessages HttpReceive web service extension is configured, and if it is not configured, to allow it, perform the following procedure.</span></span>  
  
##### <a name="to-configure-the-biztalk-isapi-extension-dll-in-iis"></a><span data-ttu-id="1b0d3-181">IIS で BizTalk ISAPI 拡張 DLL を構成するには</span><span class="sxs-lookup"><span data-stu-id="1b0d3-181">To configure the BizTalk ISAPI extension DLL in IIS</span></span>  
  
1. <span data-ttu-id="1b0d3-182">クリックして**開始**、 をポイント**管理ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-182">Click **Start**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2. <span data-ttu-id="1b0d3-183">展開**\<コンピューター名\>(ローカル コンピューター)**、 をクリックし、 **Web サービス拡張**します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-183">Expand **\<computer name\> (local computer)**, and then click **Web Service Extensions**.</span></span>  
  
3. <span data-ttu-id="1b0d3-184">**Web サービス拡張**ウィンドウで、HwsMessages HttpReceive の状態が許可されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-184">In the **Web Service Extension** pane, verify that the status for HwsMessages HttpReceive is Allowed.</span></span> <span data-ttu-id="1b0d3-185">ない場合を右クリックして**HwsMessages HttpReceive**、 をクリックし、**許可**。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-185">If not, right-click **HwsMessages HttpReceive**, and then click **Allow**.</span></span>  
  
   <span data-ttu-id="1b0d3-186">HwsMessages HttpReceive Web サービス拡張が構成されていない場合 (IIS マネージャーの Web サービス拡張一覧に含まれていない場合) は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-186">If the HwsMessages HttpReceive web service extension is not configured (it is not included in the Web Service Extensions list in IIS Manager), perform the following procedure.</span></span>  
  
##### <a name="to-configure-the-biztalk-isapi-extension-dll-in-iis"></a><span data-ttu-id="1b0d3-187">IIS で BizTalk ISAPI 拡張 DLL を構成するには</span><span class="sxs-lookup"><span data-stu-id="1b0d3-187">To configure the BizTalk ISAPI extension DLL in IIS</span></span>  
  
1.  <span data-ttu-id="1b0d3-188">クリックして**開始**、 をポイント**管理ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-188">Click **Start**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="1b0d3-189">展開**\<コンピューター名\>(ローカル コンピューター)** を右クリックして**Web サービス拡張**、 をクリックし、**新しい Web サービス拡張機能の追加**.</span><span class="sxs-lookup"><span data-stu-id="1b0d3-189">Expand **\<computer name\> (local computer)**, right-click **Web Service Extensions**, and then click **Add a new Web service extension**.</span></span>  
  
3.  <span data-ttu-id="1b0d3-190">**新しい Web サービス拡張** ダイアログ ボックスで、**拡張機能名**ボックスに「 **BizTalk ISAPI Extension**、順にクリックします**追加**します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-190">In the **New Web Service Extension** dialog box, in the **Extension Name** box, type **BizTalk ISAPI Extension**, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="1b0d3-191">**ファイルの追加** ダイアログ ボックスで、**ファイルへのパス**ボックスに「 **\<ドライブ\>: \Program Files\Microsoft BizTalk Server \<のバージョン\>\HttpReceive\BTSHttpReceive.dll**、 をクリックし、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-191">In the **Add File** dialog box, in the **Path to file** box, type **\<drive\>:\Program Files\Microsoft BizTalk Server \<version\>\HttpReceive\BTSHttpReceive.dll**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="1b0d3-192">**新しい Web サービス拡張**ダイアログ ボックスで、**拡張機能の状態を許可 に設定**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-192">In the **New Web Service Extension** dialog box, select **Set extension status to Allowed**, and then click **OK**.</span></span>  
  
## <a name="an-access-violation-occurs-when-running-the-configuration-wizard"></a><span data-ttu-id="1b0d3-193">構成ウィザードを実行するとアクセス違反が発生する</span><span class="sxs-lookup"><span data-stu-id="1b0d3-193">An access violation occurs when running the Configuration Wizard</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="1b0d3-194">現象</span><span class="sxs-lookup"><span data-stu-id="1b0d3-194">Symptom</span></span>  
 <span data-ttu-id="1b0d3-195">イベント ログに次のようなエラーが記録されます。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-195">You receive the following or similar error in the event log:</span></span>  
  
 <span data-ttu-id="1b0d3-196">ユーザー アカウント '\HostSvc' で構成された BizTalk の分離ホスト インスタンスが起動していないか、このコンピューターに存在しません。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-196">A BizTalk isolated host instance configured with the user account '\HostSvc' was either not running or does not exist on this computer.</span></span> <span data-ttu-id="1b0d3-197">BizTalk 管理コンソールを使用して、新しい分離ホストを作成するか、既存の分離ホストを再構成して、"\hostsvc" として実行してください。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-197">Use the BizTalk Administration Console to create a new isolated host or reconfigure an existing to run as '\hostsvc'.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="1b0d3-198">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="1b0d3-198">Possible Cause</span></span>  
 <span data-ttu-id="1b0d3-199">構成ウィザードを実行するユーザーを構成する必要があります '\<*マシン名*\>\hostsvc'、'\hostsvc'。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-199">To run the Configuration Wizard, the user should be configured as '\<*machine name*\>\hostsvc', not '\hostsvc'.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="1b0d3-200">解決方法</span><span class="sxs-lookup"><span data-stu-id="1b0d3-200">Solution</span></span>  
 <span data-ttu-id="1b0d3-201">BizTalk 管理コンソールを開き、アカウントで実行されるように、アカウント"\hostsvc"で実行しているホストを変更 '\<*マシン名*\>\hostsvc'。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-201">Open the BizTalk Administration Console, and change hosts that are running under the account '\hostsvc', so that they run under the account '\<*machine name*\>\hostsvc'.</span></span>  
  
## <a name="you-receive-an-error-when-importing-and-compiling-a-rosettanet-next-generation-pip-schema"></a><span data-ttu-id="1b0d3-202">RosettaNet Next Generation PIP スキーマをインポートしてコンパイルするときにエラーが発生する</span><span class="sxs-lookup"><span data-stu-id="1b0d3-202">You receive an error when importing and compiling a RosettaNet Next Generation PIP schema</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="1b0d3-203">現象</span><span class="sxs-lookup"><span data-stu-id="1b0d3-203">Symptom</span></span>  
 <span data-ttu-id="1b0d3-204">イベント ログに次のようなエラーが記録されます。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-204">You receive the following or similar error in the event log:</span></span>  
  
 <span data-ttu-id="1b0d3-205">エラー CS0234: 型または名前空間 "SerializableAttribute" は、クラスまたは名前空間 "RosettaNet.Schemas.System" に存在しません。アセンブリ参照があるかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-205">error CS0234: The type or namespace name 'SerializableAttribute' does not exist in the class or namespace 'RosettaNet.Schemas.System' (are you missing an assembly reference?).</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="1b0d3-206">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="1b0d3-206">Possible Cause</span></span>  
 <span data-ttu-id="1b0d3-207">スキーマの 1 つ、たとえば StandardDocumentHeader.xsd に、RosettaNet.Schemas.System という [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] 名前空間があります。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-207">One of your schemas, for example, StandardDocumentHeader.xsd, has a [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] namespace of RosettaNet.Schemas.System.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="1b0d3-208">解決方法</span><span class="sxs-lookup"><span data-stu-id="1b0d3-208">Solution</span></span>  
 <span data-ttu-id="1b0d3-209">このスキーマの [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] 名前空間から "System" を削除して、名前空間を RosettaNet.Schemas にします。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-209">Remove the "System" from the [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] namespace for the schema, so that the namespace is RosettaNet.Schemas.</span></span>  
  
## <a name="you-receive-an-error-when-trying-to-manually-deploy-the-bam-package"></a><span data-ttu-id="1b0d3-210">手動で BAM パッケージを展開しようとするとエラーが発生する</span><span class="sxs-lookup"><span data-stu-id="1b0d3-210">You receive an error when trying to manually deploy the BAM Package</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="1b0d3-211">現象</span><span class="sxs-lookup"><span data-stu-id="1b0d3-211">Symptom</span></span>  
 <span data-ttu-id="1b0d3-212">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] の BAM パッケージを手動で展開しようとすると、パッケージが展開できないというエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-212">When you manually try to deploy the BAM package for [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], you receive an error indicating that you cannot deploy the package.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="1b0d3-213">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="1b0d3-213">Possible Cause</span></span>  
 <span data-ttu-id="1b0d3-214">BAM_DM_Process と BAM_DM_Message という 2 つの DTS パッケージがシステムにインストールされており、これが BAM パッケージの展開を妨げています。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-214">The DTS packages BAM_DM_Process and BAM_DM_Message are installed on your system, preventing deployment of the BAM package.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="1b0d3-215">解決方法</span><span class="sxs-lookup"><span data-stu-id="1b0d3-215">Solution</span></span>  
  
##### <a name="to-recover-from-the-error-condition-and-deploy-the-bam-package"></a><span data-ttu-id="1b0d3-216">エラー状態から回復して BAM パッケージを展開するには</span><span class="sxs-lookup"><span data-stu-id="1b0d3-216">To recover from the error condition and deploy the BAM package</span></span>  
  
1.  <span data-ttu-id="1b0d3-217">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft SQL Server**、順にクリックします**Enterprise Manager**します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-217">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, and then click **Enterprise Manager**.</span></span>  
  
2.  <span data-ttu-id="1b0d3-218">Enterprise Manager で展開**Microsoft SQL Servers**、 **SQL Server グループ**、 **(ローカル) (Windows NT)**、および**データ変換サービス**.</span><span class="sxs-lookup"><span data-stu-id="1b0d3-218">In Enterprise Manager, expand **Microsoft SQL Servers**, **SQL Server Group**, **(local) (Windows NT)**, and **Data Transformation Services**.</span></span>  
  
3.  <span data-ttu-id="1b0d3-219">クリックして**ローカル パッケージ**を右クリックして**BAM_DM_Message**、順にクリックします**削除**します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-219">Click **Local Packages**, right-click **BAM_DM_Message**, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="1b0d3-220">右クリック**BAM_DM_Process**、 をクリックし、**削除**します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-220">Right-click **BAM_DM_Process**, and then click **Delete**.</span></span>  
  
5.  <span data-ttu-id="1b0d3-221">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-221">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="1b0d3-222">コマンド プロンプトで、追跡ファイルを展開する次のコードを入力し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-222">At the command prompt, type the following code to deploy the tracking file, and then click **OK**.</span></span>  
  
    ```  
    cd %ProgramFiles%\Microsoft BizTalk Server <version>\Tracking  
    bm deploy all  "%ProgramFiles%\Microsoft BizTalk <version> Accelerator for RosettaNet\BAMTracking\tracking.xml"  
    ```  
  
## <a name="you-receive-an-error-when-adding-a-new-pip"></a><span data-ttu-id="1b0d3-223">新しい PIP を追加するときにエラーが表示される</span><span class="sxs-lookup"><span data-stu-id="1b0d3-223">You receive an error when adding a new PIP</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="1b0d3-224">現象</span><span class="sxs-lookup"><span data-stu-id="1b0d3-224">Symptom</span></span>  
 <span data-ttu-id="1b0d3-225">イベント ログに次のようなエラーが記録されます。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-225">You receive the following or similar error in the event log:</span></span>  
  
 <span data-ttu-id="1b0d3-226">Service Content の検証中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-226">UNP.SCON.VALERR: A failure occurred while validating the service content.</span></span>  
  
 <span data-ttu-id="1b0d3-227">詳細: ドキュメント仕様をメッセージの種類別に検索できませんでした。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-227">Details: Finding document specification by message type failed.</span></span> <span data-ttu-id="1b0d3-228">スキーマが正しく展開されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-228">Verify that the schema is deployed properly.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="1b0d3-229">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="1b0d3-229">Possible Cause</span></span>  
 <span data-ttu-id="1b0d3-230">インスタンス Pip4A5NotifyofForecastReply の展開済みスキーマのドキュメント名前空間か、ルート ノード プロパティのどちらかが間違っています。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-230">Either the document namespace or the root node property the deployed schema for the instance Pip4A5NotifyofForecastReply is incorrect.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="1b0d3-231">解決方法</span><span class="sxs-lookup"><span data-stu-id="1b0d3-231">Solution</span></span>  
 <span data-ttu-id="1b0d3-232">インスタンス Pip4A5NotifyofForecastReply の展開済みスキーマのドキュメント名前空間とルート ノード プロパティが正しいかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-232">Verify that the document namespace and the root node property for the deployed schema for instance Pip4A5NotifyofForecastReply is correct.</span></span>  
  
## <a name="error-during-the-configuration-of-btarn-at-installation-time-caused-by-presumed-network-connectivity-issues"></a><span data-ttu-id="1b0d3-233">インストール時の BTARN を構成中にネットワーク接続の問題が推定されてエラーが発生する</span><span class="sxs-lookup"><span data-stu-id="1b0d3-233">Error during the configuration of BTARN at installation time, caused by presumed network connectivity issues</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="1b0d3-234">現象</span><span class="sxs-lookup"><span data-stu-id="1b0d3-234">Symptom</span></span>  
 <span data-ttu-id="1b0d3-235">構成プロセス中に、コンピュータが実際にはネットワークに正しく接続されているのに正しく接続されていないというエラーが [エラー] ダイアログ ボックスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-235">During the configuration process, you receive an error in the error dialog box indicating that the computer is not properly connected to the network, when in fact it is.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="1b0d3-236">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="1b0d3-236">Possible Cause</span></span>  
 <span data-ttu-id="1b0d3-237">このエラーは、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 構成プログラムが IP アドレスの解釈を間違えると発生します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-237">This error may be caused by the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] configuration program misinterpreting IP addresses.</span></span> <span data-ttu-id="1b0d3-238">C:\Windows\system32\drivers\etc に格納されているホスト ファイルには、localhost のホスト名を IP アドレス 127.0.0.1 にマップしているエントリが記載されています。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-238">The hosts file in C:\Windows\system32\drivers\etc contains an entry mapping the localhost host name to the IP address 127.0.0.1.</span></span> <span data-ttu-id="1b0d3-239">構成プログラムが、この値をループバック アドレスの値と混同した結果、コンピュータがネットワークに正しく接続されていないと誤認している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-239">The configuration program may confuse this value with the loopback address, and assume that the computer is not connected properly to the network.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="1b0d3-240">解決方法</span><span class="sxs-lookup"><span data-stu-id="1b0d3-240">Solution</span></span>  
  
##### <a name="to-avoid-this-error-and-complete-the-configuration-process"></a><span data-ttu-id="1b0d3-241">このエラーを回避して構成プロセスを完了するには</span><span class="sxs-lookup"><span data-stu-id="1b0d3-241">To avoid this error and complete the configuration process</span></span>  
  
1. <span data-ttu-id="1b0d3-242">[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] エクスプローラーで、C:\Windows\system32\drivers\etc に移動し、メモ帳を使用してホスト ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-242">In [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, move to C:\Windows\system32\drivers\etc, and open the hosts file using Notepad.</span></span>  
  
2. <span data-ttu-id="1b0d3-243">行をコメント アウト"127.0.0.1 localhost"の行の先頭に「#」を配置することで。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-243">Comment out the line "127.0.0.1        localhost" by placing "# " at the start of the line.</span></span> <span data-ttu-id="1b0d3-244">変更されたホスト ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-244">Save the changed hosts file.</span></span>  
  
3. <span data-ttu-id="1b0d3-245">クリックして**再試行**エラー ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-245">Click **Retry** in the error dialog box.</span></span>  
  
4. <span data-ttu-id="1b0d3-246">構成が正常に完了した後で、メモ帳でホスト ファイルを再び開き、localhost をマップしている行の行頭に付けたコメント記号を削除して、ホスト ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-246">After configuration has completed successfully, re-open the hosts file in Notepad, remove the comment mark at the start of the line mapping localhost, and then save the hosts file.</span></span>  
  
## <a name="you-receive-an-error-regarding-incorrect-signature-length"></a><span data-ttu-id="1b0d3-247">署名の長さが正しくないというエラーが表示される</span><span class="sxs-lookup"><span data-stu-id="1b0d3-247">You receive an error regarding incorrect signature length</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="1b0d3-248">現象</span><span class="sxs-lookup"><span data-stu-id="1b0d3-248">Symptom</span></span>  
 <span data-ttu-id="1b0d3-249">イベント ログに次のようなエラーが記録されます。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-249">You receive the following or similar error in the event log:</span></span>  
  
 <span data-ttu-id="1b0d3-250">受信パイプライン "Microsoft.Solutions.BTARN.Pipelines.Receive" を実行中にエラーが発生しました。送信元: "MIME/SMIME decoder"、受信ポート: "/BTARNHttpReceive/BTSHTTPReceive.dll?xRNResponseType=async"、理由: 不正な署名の長さ、値 = 1935897193。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-250">There was a failure executing the receive pipeline: "Microsoft.Solutions.BTARN.Pipelines.Receive" Source: "MIME/SMIME decoder" Receive Location: "/BTARNHttpReceive/BTSHTTPReceive.dll?xRNResponseType=async" Reason: Incorrect signature length, value = 1935897193.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="1b0d3-251">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="1b0d3-251">Possible Cause</span></span>  
 <span data-ttu-id="1b0d3-252">このエラー メッセージは、署名の長さが間違っていることを通知します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-252">This error message indicates that the signature length is incorrect.</span></span> <span data-ttu-id="1b0d3-253">このエラーは上記の原因の他に、ヘッダー内容の長さの間違いや不完全によっても発生します。これが原因で署名の長さのバイト数が誤って読み取られます。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-253">In addition to the above cause, this error could also due to the incorrect or incomplete header content length which leads to the wrong bytes read on the signature length.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="1b0d3-254">解決方法</span><span class="sxs-lookup"><span data-stu-id="1b0d3-254">Solution</span></span>  
 <span data-ttu-id="1b0d3-255">署名とヘッダー内容の両方の長さが正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-255">Verify that both of the signature length and header content length is correct.</span></span>  
  
## <a name="you-receive-503-service-unavailable-from-internet-explorer-on-64-bit-machine"></a><span data-ttu-id="1b0d3-256">64 ビット マシンで、Internet Explorer に "503: Service Unavailable" というメッセージが表示される</span><span class="sxs-lookup"><span data-stu-id="1b0d3-256">You receive "503: Service Unavailable" from Internet Explorer on 64-bit machine</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="1b0d3-257">現象</span><span class="sxs-lookup"><span data-stu-id="1b0d3-257">Symptom</span></span>  
 <span data-ttu-id="1b0d3-258">後[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]にアクセスしようとすると、構成が完了した [http://localhost](http://localhost/) または [http://localhost/BtarnApp/RnifSend.aspx](http://localhost/BtarnApp/RnifSend.aspx)、以下のようなエラーが発生した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-258">After [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] configuration is completed, when you try to access [http://localhost](http://localhost/) or [http://localhost/BtarnApp/RnifSend.aspx](http://localhost/BtarnApp/RnifSend.aspx), you may receive the following or similar error:</span></span>  
  
 <span data-ttu-id="1b0d3-259">503: Service Unavailable</span><span class="sxs-lookup"><span data-stu-id="1b0d3-259">503: Service Unavailable</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="1b0d3-260">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="1b0d3-260">Possible Cause</span></span>  
 <span data-ttu-id="1b0d3-261">このエラーは、C:\windows\system32\rpcproxy\rpcproxy.dll の IIS Web サイトに設定されている ISAPI フィルターが原因で発生します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-261">This error may be caused by the ISAPI filter found under C:\windows\system32\rpcproxy\rpcproxy.dll being set on IIS Web Sites.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="1b0d3-262">解決方法</span><span class="sxs-lookup"><span data-stu-id="1b0d3-262">Solution</span></span>  
  
##### <a name="to-remove-rpcproxy-filter-entry-in-iis"></a><span data-ttu-id="1b0d3-263">IIS で RpcProxy フィルターを削除するには</span><span class="sxs-lookup"><span data-stu-id="1b0d3-263">To remove RpcProxy filter entry in IIS</span></span>  
  
1.  <span data-ttu-id="1b0d3-264">クリックして**開始**、 をポイント**管理ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-264">Click **Start**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="1b0d3-265">展開**\<コンピューター名\>(ローカル コンピューター)** を右クリックして**Websites**、順にクリックします**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-265">Expand **\<computer name\> (local computer)**, right-click **Web Sites**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="1b0d3-266">選択**ISAPI フィルター**タブ。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-266">Select **ISAPI Filters** tab.</span></span>  
  
4.  <span data-ttu-id="1b0d3-267">選択**RpcProxy フィルター**、 をクリック**削除**します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-267">Select **RpcProxy filter**, and click **Remove**.</span></span>  
  
5.  <span data-ttu-id="1b0d3-268">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-268">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="1b0d3-269">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-269">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="1b0d3-270">コマンド プロンプトで、次のコードを入力して IIS をリセットします。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-270">At the command prompt, type the following code to reset IIS.</span></span>  
  
    ```  
    iisreset  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="1b0d3-271">アクセスしようとする場合 http://localhost または http://localhost/BtarnApp/RnifSend.aspx もう一度上記の手順を実行すると、メッセージが表示されます HTTP 400 から Internet Explorer は IIS が正しく機能しています。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-271">If you try to access http://localhost or http://localhost/BtarnApp/RnifSend.aspx again after performing the above steps, you will receive HTTP 400 message back from the Internet Explorer which means that IIS is now functioning properly.</span></span>  
  
## <a name="the-hubscenario-sample-will-not-be-installed-correctly-if-the-assembly-key-files-are-not-entered-for-the-projects"></a><span data-ttu-id="1b0d3-272">アセンブリ キー ファイルがプロジェクトに入力されていない場合に HubScenario サンプルが正しくインストールされない</span><span class="sxs-lookup"><span data-stu-id="1b0d3-272">The HubScenario sample will not be installed correctly if the assembly key files are not entered for the projects</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="1b0d3-273">現象</span><span class="sxs-lookup"><span data-stu-id="1b0d3-273">Symptom</span></span>  
 <span data-ttu-id="1b0d3-274">Setup.bat を実行すると*\<ドライブ\>*: \Program Files\\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\hubscenario を設定するにはHubScenario サンプルでは、操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-274">When you run setup.bat in *\<drive\>*:\Program Files\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK\HubScenario to set up the HubScenario sample, the operation fails.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="1b0d3-275">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="1b0d3-275">Possible Cause</span></span>  
 <span data-ttu-id="1b0d3-276">アセンブリ キー ファイルがプロジェクトに設定されていないので、HubScenario および HubHelper アセンブリが正しく展開されていません。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-276">The HubScenario and HubHelper assemblies were not deployed correctly because the assembly key files were not set in the projects.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="1b0d3-277">解決方法</span><span class="sxs-lookup"><span data-stu-id="1b0d3-277">Solution</span></span>  
 <span data-ttu-id="1b0d3-278">HubScenario および HubHelper プロジェクトのアセンブリ キー ファイルを設定します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-278">Set the assembly key files for the HubScenario and HubHelper projects.</span></span> <span data-ttu-id="1b0d3-279">詳細については、次を参照してください。 [HubScenario サンプル](../../adapters-and-accelerators/accelerator-rosettanet/hubscenario-sample.md)します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-279">For more information, see [HubScenario Sample](../../adapters-and-accelerators/accelerator-rosettanet/hubscenario-sample.md).</span></span>  
  
## <a name="run-setupx64bat-to-set-up-the-double-action-pipautomation-orchestration-sample-on-sql-server-2008-r22008-sp1"></a><span data-ttu-id="1b0d3-280">SQL Server 2008 R2 または SQL Server 2008 SP1 で setupx64.bat を実行して Double Action PIPAutomation オーケストレーション サンプルを設定する</span><span class="sxs-lookup"><span data-stu-id="1b0d3-280">Run setupx64.bat to set up the Double Action PIPAutomation Orchestration sample on SQL Server 2008 R2/2008 SP1</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="1b0d3-281">現象</span><span class="sxs-lookup"><span data-stu-id="1b0d3-281">Symptom</span></span>  
 <span data-ttu-id="1b0d3-282">setup.bat を実行して Double Action PIPAutomation オーケストレーション サンプルを構築および初期化しようとしたときに、BTARNData データベースに PipAutomationGetAction ストアド プロシージャが作成されない。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-282">When you run setup.bat to build and initialize the Double Action PIPAutomation Orchestration sample, the PipAutomationGetAction stored procedure in the BTARNData database is not created.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="1b0d3-283">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="1b0d3-283">Possible Cause</span></span>  
 <span data-ttu-id="1b0d3-284">64 ビット コンピューターで、または SQL Server 2008 R2 または 2008 SP1 で実行されている BizTalk Server のインストールでは、setup.bat を実行します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-284">You ran setup.bat on a 64-bit computer or on a BizTalk Server installation that is running on SQL Server 2008 R2/2008 SP1.</span></span> <span data-ttu-id="1b0d3-285">これらのインスタンスでは setupx64.bat を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-285">Both of these instances require you to run setupx64.bat.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="1b0d3-286">解決方法</span><span class="sxs-lookup"><span data-stu-id="1b0d3-286">Solution</span></span>  
 <span data-ttu-id="1b0d3-287">setupx64.bat を実行してストアド プロシージャを作成します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-287">Run setupx64.bat to create the stored procedure.</span></span> <span data-ttu-id="1b0d3-288">詳細については、次を参照してください。 [Double Action PIPAutomation Orchestration](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md)します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-288">For more information, see [Double Action PIPAutomation Orchestration](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md).</span></span>  
  
## <a name="enable-the-btarn-application-pools-for-32-bit-on-windows-server-2008-64-bit-windows-operating-system-os"></a><span data-ttu-id="1b0d3-289">64 ビットの Windows オペレーティング システム (OS) の Windows Server 2008 で 32 ビットの BTARN アプリケーション プールを有効にする</span><span class="sxs-lookup"><span data-stu-id="1b0d3-289">Enable the BTARN Application Pools for 32 bit on Windows Server 2008, 64-bit Windows Operating System (OS)</span></span>  
 <span data-ttu-id="1b0d3-290">インターネット インフォメーション サービス マネージャー 7.5 または 7.0 を使用して、64 ビットの Windows オペレーティング システム (OS) の Windows Server 2008 で BTARN エンド ツー エンド シナリオを実行するには</span><span class="sxs-lookup"><span data-stu-id="1b0d3-290">To run the BTARN End to End scenario on Windows Server 2008,64-bit Windows Operating System (OS), Internet Information Services Manager 7.5/7.0.</span></span>  
  
 1. <span data-ttu-id="1b0d3-291">32 ビットの BTARN アプリケーション プールを有効にします。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-291">Enable the BTARN Application Pools for 32 bit.</span></span>  
  
 2. <span data-ttu-id="1b0d3-292">IsapiModule フィルターを参照する \*.dll の HTTP ハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="1b0d3-292">Add a HTTP Handler for \*.dll refering the IsapiModule Filters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b0d3-293">参照</span><span class="sxs-lookup"><span data-stu-id="1b0d3-293">See Also</span></span>  
 <span data-ttu-id="1b0d3-294">[BtarnClean](../../adapters-and-accelerators/accelerator-rosettanet/btarnclean.md) </span><span class="sxs-lookup"><span data-stu-id="1b0d3-294">[BtarnClean](../../adapters-and-accelerators/accelerator-rosettanet/btarnclean.md) </span></span>  
 [<span data-ttu-id="1b0d3-295">Loopback</span><span class="sxs-lookup"><span data-stu-id="1b0d3-295">Loopback</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/loopback.md)